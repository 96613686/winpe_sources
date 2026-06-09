# CWIMFile::Create(ushort const *,ulong,ulong,ulong,ulong,ulong *)

- ea: `0x18000e39c`
- end: `0x18000e479`
- name: `?Create@CWIMFile@@QEAAKPEBGKKKKPEAK@Z`
- size: `221`
- prototype: `unsigned int __usercall@<eax>(CWIMFile *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int, unsigned int, unsigned int *)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180008e70`
- `0x1800096c0`
- `0x18000bc58`

## callees

- `0x18000e39c`
- `0x18000e480`
- `0x18000e4e4`
- `0x18000e5f0`
- `0x18000e688`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000e3f9`
- `KERNEL32!GetLastError` at `0x18000e3f9`
- `WIMGAPI!WIMCreateFile` at `0x18000e3e5`
- `WIMGAPI!WIMCreateFile` at `0x18000e3e5`

## pseudocode

```c
__int64 __fastcall CWIMFile::Create(
        CWIMFile *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int *a7)
{
  __int64 v11; // rax
  DWORD LastError; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  unsigned int FileSize; // ebx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // r8
  unsigned int v21; // [rsp+40h] [rbp+8h] BYREF

  v21 = 0;
  CWIMFile::Shutdown(this);
  v11 = WIMCreateFile(a2, a3, a4, a5, a6, &v21);
  *(_QWORD *)this = v11;
  if ( v11 )
  {
    FileSize = CWIMFile::SetTempFolder(this);
    if ( !(unsigned int)ElValidateWin32_5(FileSize, v16, v17, 138) )
    {
      FileSize = CWIMFile::QueryFileSize(this, (unsigned __int64 *)this + 1);
      if ( !(unsigned int)ElValidateWin32_5(FileSize, v18, v19, 144) )
      {
        if ( a7 )
          *a7 = v21;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    return (unsigned int)ElValidateWin32_5(LastError, v13, v14, 130);
  }
  return FileSize;
}

```

## disassembly

```asm
0x18000e39c  mov     rax, rsp
0x18000e39f  mov     [rax+10h], rbx
0x18000e3a3  mov     [rax+18h], rsi
0x18000e3a7  mov     [rax+20h], rdi
0x18000e3ab  push    r14
0x18000e3ad  sub     rsp, 30h
0x18000e3b1  and     dword ptr [rax+8], 0
0x18000e3b5  mov     ebx, r9d
0x18000e3b8  mov     edi, r8d
0x18000e3bb  mov     rsi, rdx
0x18000e3be  mov     r14, rcx
0x18000e3c1  call    ?Shutdown@CWIMFile@@QEAAKXZ; CWIMFile::Shutdown(void)
0x18000e3c6  mov     r9d, [rsp+38h+arg_20]
0x18000e3cb  lea     rax, [rsp+38h+arg_0]
0x18000e3d0  mov     [rsp+38h+var_10], rax
0x18000e3d5  mov     r8d, ebx
0x18000e3d8  mov     eax, [rsp+38h+arg_28]
0x18000e3dc  mov     edx, edi
0x18000e3de  mov     rcx, rsi
0x18000e3e1  mov     [rsp+38h+var_18], eax
0x18000e3e5  call    cs:__imp_WIMCreateFile
0x18000e3ec  nop     dword ptr [rax+rax+00h]
0x18000e3f1  mov     [r14], rax
0x18000e3f4  test    rax, rax
0x18000e3f7  jnz     short loc_18000E416
0x18000e3f9  call    cs:__imp_GetLastError
0x18000e400  nop     dword ptr [rax+rax+00h]
0x18000e405  mov     ecx, eax
0x18000e407  mov     r9d, 82h
0x18000e40d  call    ElValidateWin32_5
0x18000e412  mov     ebx, eax
0x18000e414  jmp     short loc_18000E460
0x18000e416  mov     rcx, r14; this
0x18000e419  call    ?SetTempFolder@CWIMFile@@AEAAKXZ; CWIMFile::SetTempFolder(void)
0x18000e41e  mov     r9d, 8Ah
0x18000e424  mov     ecx, eax
0x18000e426  mov     ebx, eax
0x18000e428  call    ElValidateWin32_5
0x18000e42d  test    eax, eax
0x18000e42f  jnz     short loc_18000E460
0x18000e431  lea     rdx, [r14+8]; unsigned __int64 *
0x18000e435  mov     rcx, r14; this
0x18000e438  call    ?QueryFileSize@CWIMFile@@AEAAKPEA_K@Z; CWIMFile::QueryFileSize(unsigned __int64 *)
0x18000e43d  mov     r9d, 90h
0x18000e443  mov     ecx, eax
0x18000e445  mov     ebx, eax
0x18000e447  call    ElValidateWin32_5
0x18000e44c  test    eax, eax
0x18000e44e  jnz     short loc_18000E460
0x18000e450  mov     rcx, [rsp+38h+arg_30]
0x18000e455  test    rcx, rcx
0x18000e458  jz      short loc_18000E460
0x18000e45a  mov     eax, [rsp+38h+arg_0]
0x18000e45e  mov     [rcx], eax
0x18000e460  mov     rsi, [rsp+38h+arg_10]
0x18000e465  mov     eax, ebx
0x18000e467  mov     rbx, [rsp+38h+arg_8]
0x18000e46c  mov     rdi, [rsp+38h+arg_18]
0x18000e471  add     rsp, 30h
0x18000e475  pop     r14
0x18000e477  retn
```
