# RemoveSignedDataMsg(SIP_SUBJECTINFO_ *,ulong)

- ea: `0x180009be0`
- end: `0x180009cbf`
- name: `?RemoveSignedDataMsg@@YAHPEAUSIP_SUBJECTINFO_@@K@Z`
- size: `223`
- prototype: `__int64 __fastcall(struct SIP_SUBJECTINFO_ *, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180001220`
- `0x180001270`
- `0x180001940`
- `0x180001b30`
- `0x1800021d0`
- `0x180009078`
- `0x180009be0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180009c18`
- `KERNEL32!GetLastError` at `0x180009c18`
- `KERNEL32!CloseHandle` at `0x180009c9b`
- `KERNEL32!CloseHandle` at `0x180009c9b`
- `KERNEL32!SetLastError` at `0x180009ca7`
- `KERNEL32!SetLastError` at `0x180009ca7`

## pseudocode

```c
__int64 __fastcall RemoveSignedDataMsg(struct SIP_SUBJECTINFO_ *a1, int a2)
{
  unsigned int v4; // edi
  DWORD LastError; // ebx
  unsigned int v6; // esi
  void *Src; // [rsp+20h] [rbp-18h] BYREF
  HANDLE hObject; // [rsp+50h] [rbp+18h] BYREF
  unsigned __int16 *v10; // [rsp+58h] [rbp+20h] BYREF

  hObject = 0;
  v10 = 0;
  Src = 0;
  v4 = 0;
  if ( !(unsigned int)VerifySubjectInfo() )
    goto LABEL_2;
  if ( a2 )
  {
    LastError = 87;
  }
  else
  {
    v6 = ClassifyGuid(a1->pgSubjectType);
    if ( !(unsigned int)GetFileHandleFromSubject(a1, 3221225472LL, &hObject)
      || !(unsigned int)FileToBstr(hObject, (__int64)&v10)
      || !(unsigned int)StripSignature(v10, v6, (OLECHAR **)&Src, 0)
      || !(unsigned int)BstrToFile(hObject, Src) )
    {
LABEL_2:
      LastError = GetLastError();
      goto LABEL_10;
    }
    LastError = 0;
    v4 = 1;
  }
LABEL_10:
  if ( hObject )
    CloseHandle(hObject);
  if ( !v4 )
    SetLastError(LastError);
  return v4;
}

```

## disassembly

```asm
0x180009be0  mov     rax, rsp
0x180009be3  mov     [rax+8], rbx
0x180009be7  mov     [rax+10h], rsi
0x180009beb  push    rdi
0x180009bec  sub     rsp, 30h
0x180009bf0  mov     esi, edx
0x180009bf2  mov     qword ptr [rax+18h], 0
0x180009bfa  mov     rbx, rcx
0x180009bfd  mov     qword ptr [rax+20h], 0
0x180009c05  mov     qword ptr [rax-18h], 0
0x180009c0d  xor     edi, edi
0x180009c0f  call    VerifySubjectInfo
0x180009c14  test    eax, eax
0x180009c16  jnz     short loc_180009C22
0x180009c18  call    cs:__imp_GetLastError
0x180009c1e  mov     ebx, eax
0x180009c20  jmp     short loc_180009C91
0x180009c22  test    esi, esi
0x180009c24  jz      short loc_180009C2D
0x180009c26  mov     ebx, 57h ; 'W'
0x180009c2b  jmp     short loc_180009C91
0x180009c2d  mov     rcx, [rbx+8]
0x180009c31  call    ClassifyGuid
0x180009c36  mov     edx, 0C0000000h
0x180009c3b  lea     r8, [rsp+38h+hObject]
0x180009c40  mov     rcx, rbx
0x180009c43  mov     esi, eax
0x180009c45  call    GetFileHandleFromSubject
0x180009c4a  test    eax, eax
0x180009c4c  jz      short loc_180009C18
0x180009c4e  mov     rcx, [rsp+38h+hObject]; hFile
0x180009c53  lea     rdx, [rsp+38h+arg_18]
0x180009c58  call    FileToBstr
0x180009c5d  test    eax, eax
0x180009c5f  jz      short loc_180009C18
0x180009c61  mov     rcx, [rsp+38h+arg_18]; unsigned __int16 *
0x180009c66  lea     r8, [rsp+38h+Src]
0x180009c6b  xor     r9d, r9d
0x180009c6e  mov     edx, esi
0x180009c70  call    StripSignature
0x180009c75  test    eax, eax
0x180009c77  jz      short loc_180009C18
0x180009c79  mov     rdx, [rsp+38h+Src]; Src
0x180009c7e  mov     rcx, [rsp+38h+hObject]; hFile
0x180009c83  call    BstrToFile
0x180009c88  test    eax, eax
0x180009c8a  jz      short loc_180009C18
0x180009c8c  xor     ebx, ebx
0x180009c8e  lea     edi, [rbx+1]
0x180009c91  mov     rcx, [rsp+38h+hObject]; hObject
0x180009c96  test    rcx, rcx
0x180009c99  jz      short loc_180009CA1
0x180009c9b  call    cs:__imp_CloseHandle
0x180009ca1  test    edi, edi
0x180009ca3  jnz     short loc_180009CAD
0x180009ca5  mov     ecx, ebx; dwErrCode
0x180009ca7  call    cs:__imp_SetLastError
0x180009cad  mov     rbx, [rsp+38h+arg_0]
0x180009cb2  mov     eax, edi
0x180009cb4  mov     rsi, [rsp+38h+arg_8]
0x180009cb9  add     rsp, 30h
0x180009cbd  pop     rdi
0x180009cbe  retn
```
