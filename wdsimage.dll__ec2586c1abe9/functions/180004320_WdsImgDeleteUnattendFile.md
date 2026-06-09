# WdsImgDeleteUnattendFile

- ea: `0x180004320`
- end: `0x1800043c9`
- name: `WdsImgDeleteUnattendFile`
- size: `169`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180003c68`
- `0x180004320`
- `0x1800083b4`
- `0x18000d6b0`
- `0x180011010`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x180004358`
- `KERNEL32!DeleteFileW` at `0x180004358`
- `KERNEL32!GetLastError` at `0x180004368`
- `KERNEL32!GetLastError` at `0x180004368`

## pseudocode

```c
__int64 __fastcall WdsImgDeleteUnattendFile(void *a1)
{
  __int64 ImageFromHandle; // rbx
  __int64 v2; // rdx
  __int64 v3; // r8
  int v4; // eax
  struct CImage *v5; // rdi
  __int64 v6; // rdx
  __int64 v7; // r8
  DWORD LastError; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  int v11; // eax
  struct CImage *v13; // [rsp+38h] [rbp+10h] BYREF

  v13 = 0;
  ImageFromHandle = (unsigned int)CEnumImages::GetImageFromHandle(a1, &v13);
  v4 = ElValidateHr_0(ImageFromHandle, v2, v3, 1465);
  v5 = v13;
  if ( v4 >= 0 )
  {
    LODWORD(ImageFromHandle) = 0;
    if ( !DeleteFileW(*((LPCWSTR *)v13 + 13)) )
    {
      LastError = GetLastError();
      v11 = ElValidateWin32_4(LastError, v9, v10, 1558);
      LODWORD(ImageFromHandle) = v11;
      if ( v11 > 0 )
        LODWORD(ImageFromHandle) = (unsigned __int16)v11 | 0x80070000;
      if ( (int)ImageFromHandle >= 0 )
        LODWORD(ImageFromHandle) = -2147467259;
    }
    ElValidateHr_0((unsigned int)ImageFromHandle, v6, v7, 1468);
  }
  if ( v5 )
    (*(void (__fastcall **)(struct CImage *))(*(_QWORD *)v5 + 8LL))(v5);
  return (unsigned int)ImageFromHandle;
}

```

## disassembly

```asm
0x180004320  mov     [rsp+arg_0], rbx
0x180004325  push    rdi
0x180004326  sub     rsp, 20h
0x18000432a  and     [rsp+28h+arg_8], 0
0x180004330  lea     rdx, [rsp+28h+arg_8]; struct CImage **
0x180004335  call    ?GetImageFromHandle@CEnumImages@@SAJPEAXPEAPEAVCImage@@@Z; CEnumImages::GetImageFromHandle(void *,CImage * *)
0x18000433a  mov     r9d, 5B9h
0x180004340  mov     ecx, eax
0x180004342  mov     ebx, eax
0x180004344  call    ElValidateHr_0
0x180004349  mov     rdi, [rsp+28h+arg_8]
0x18000434e  test    eax, eax
0x180004350  js      short loc_1800043A7
0x180004352  mov     rcx, [rdi+68h]; lpFileName
0x180004356  xor     ebx, ebx
0x180004358  call    cs:__imp_DeleteFileW
0x18000435f  nop     dword ptr [rax+rax+00h]
0x180004364  test    eax, eax
0x180004366  jnz     short loc_18000439A
0x180004368  call    cs:__imp_GetLastError
0x18000436f  nop     dword ptr [rax+rax+00h]
0x180004374  mov     ecx, eax
0x180004376  mov     r9d, 616h
0x18000437c  call    ElValidateWin32_4
0x180004381  mov     ebx, eax
0x180004383  test    eax, eax
0x180004385  jle     short loc_180004390
0x180004387  movzx   ebx, ax
0x18000438a  or      ebx, 80070000h
0x180004390  test    ebx, ebx
0x180004392  mov     eax, 80004005h
0x180004397  cmovns  ebx, eax
0x18000439a  mov     r9d, 5BCh
0x1800043a0  mov     ecx, ebx
0x1800043a2  call    ElValidateHr_0
0x1800043a7  test    rdi, rdi
0x1800043aa  jz      short loc_1800043BB
0x1800043ac  mov     rax, [rdi]
0x1800043af  mov     rcx, rdi
0x1800043b2  mov     rax, [rax+8]
0x1800043b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043bb  mov     eax, ebx
0x1800043bd  mov     rbx, [rsp+28h+arg_0]
0x1800043c2  add     rsp, 20h
0x1800043c6  pop     rdi
0x1800043c7  retn
```
