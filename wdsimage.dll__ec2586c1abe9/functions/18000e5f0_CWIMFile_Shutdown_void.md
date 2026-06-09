# CWIMFile::Shutdown(void)

- ea: `0x18000e5f0`
- end: `0x18000e680`
- name: `?Shutdown@CWIMFile@@QEAAKXZ`
- size: `144`
- prototype: `unsigned int __fastcall(CWIMFile *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180008e70`
- `0x1800096c0`
- `0x18000bc58`
- `0x18000e39c`

## callees

- `0x18000e5f0`
- `0x18000e688`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000e620`
- `KERNEL32!GetLastError` at `0x18000e657`
- `KERNEL32!GetLastError` at `0x18000e620`
- `KERNEL32!GetLastError` at `0x18000e657`
- `WIMGAPI!WIMCloseHandle` at `0x18000e647`
- `WIMGAPI!WIMCloseHandle` at `0x18000e647`
- `WIMGAPI!WIMUnregisterMessageCallback` at `0x18000e610`
- `WIMGAPI!WIMUnregisterMessageCallback` at `0x18000e610`

## pseudocode

```c
__int64 __fastcall CWIMFile::Shutdown(CWIMFile *this)
{
  unsigned int v1; // ebx
  DWORD LastError; // eax
  __int64 v4; // rdx
  __int64 v5; // r8
  unsigned int v6; // r9d

  v1 = 0;
  if ( *(_QWORD *)this )
  {
    if ( *((_DWORD *)this + 4) )
    {
      if ( !(unsigned int)WIMUnregisterMessageCallback(*(_QWORD *)this, *((_QWORD *)this + 3)) )
      {
        LastError = GetLastError();
        v6 = 279;
        return (unsigned int)ElValidateWin32_5(LastError, v4, v5, v6);
      }
      *((_DWORD *)this + 4) = 0;
      *((_QWORD *)this + 3) = 0;
    }
    if ( (unsigned int)WIMCloseHandle(*(_QWORD *)this) )
    {
      *(_QWORD *)this = 0;
      *((_QWORD *)this + 1) = 0;
      return v1;
    }
    LastError = GetLastError();
    v6 = 288;
    return (unsigned int)ElValidateWin32_5(LastError, v4, v5, v6);
  }
  return v1;
}

```

## disassembly

```asm
0x18000e5f0  mov     [rsp+arg_0], rbx
0x18000e5f5  push    rdi
0x18000e5f6  sub     rsp, 20h
0x18000e5fa  xor     ebx, ebx
0x18000e5fc  mov     rdi, rcx
0x18000e5ff  cmp     [rcx], rbx
0x18000e602  jz      short loc_18000E672
0x18000e604  cmp     [rcx+10h], ebx
0x18000e607  jz      short loc_18000E644
0x18000e609  mov     rdx, [rcx+18h]
0x18000e60d  mov     rcx, [rcx]
0x18000e610  call    cs:__imp_WIMUnregisterMessageCallback
0x18000e617  nop     dword ptr [rax+rax+00h]
0x18000e61c  test    eax, eax
0x18000e61e  jnz     short loc_18000E63D
0x18000e620  call    cs:__imp_GetLastError
0x18000e627  nop     dword ptr [rax+rax+00h]
0x18000e62c  mov     r9d, 117h
0x18000e632  mov     ecx, eax
0x18000e634  call    ElValidateWin32_5
0x18000e639  mov     ebx, eax
0x18000e63b  jmp     short loc_18000E672
0x18000e63d  mov     [rdi+10h], ebx
0x18000e640  mov     [rdi+18h], rbx
0x18000e644  mov     rcx, [rdi]
0x18000e647  call    cs:__imp_WIMCloseHandle
0x18000e64e  nop     dword ptr [rax+rax+00h]
0x18000e653  test    eax, eax
0x18000e655  jnz     short loc_18000E66B
0x18000e657  call    cs:__imp_GetLastError
0x18000e65e  nop     dword ptr [rax+rax+00h]
0x18000e663  mov     r9d, 120h
0x18000e669  jmp     short loc_18000E632
0x18000e66b  mov     [rdi], rbx
0x18000e66e  mov     [rdi+8], rbx
0x18000e672  mov     eax, ebx
0x18000e674  mov     rbx, [rsp+28h+arg_0]
0x18000e679  add     rsp, 20h
0x18000e67d  pop     rdi
0x18000e67e  retn
```
