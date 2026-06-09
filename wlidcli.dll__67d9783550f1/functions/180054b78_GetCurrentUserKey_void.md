# GetCurrentUserKey(void)

- ea: `0x180054b78`
- end: `0x180054bf9`
- name: `?GetCurrentUserKey@@YA?AVCRegKey@ATL@@XZ`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000d5c0`

## callees

- `0x1800039f0`
- `0x180054b78`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180054bbd`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180054bbd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall GetCurrentUserKey(_QWORD *a1)
{
  int v2; // eax
  int pExceptionObject; // [rsp+48h] [rbp+10h] BYREF
  HKEY v5; // [rsp+50h] [rbp+18h] BYREF

  v5 = 0;
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  v2 = RegOpenCurrentUser(0x2000000u, &v5);
  if ( v2 )
  {
    if ( v2 > 0 )
      v2 = (unsigned __int16)v2 | 0x80070000;
    pExceptionObject = v2;
    throw (long *)&pExceptionObject;
  }
  *a1 = v5;
  return a1;
}

```

## disassembly

```asm
0x180054b78  mov     rax, rsp
0x180054b7b  mov     [rax+8], rcx
0x180054b7f  push    rbx
0x180054b80  sub     rsp, 30h
0x180054b84  mov     rbx, rcx
0x180054b87  mov     dword ptr [rax-18h], 0
0x180054b8e  mov     qword ptr [rax+18h], 0
0x180054b96  mov     qword ptr [rcx], 0
0x180054b9d  mov     qword ptr [rcx+8], 0
0x180054ba5  mov     qword ptr [rcx+10h], 0
0x180054bad  mov     dword ptr [rax-18h], 1
0x180054bb4  lea     rdx, [rax+18h]; phkResult
0x180054bb8  mov     ecx, 2000000h; samDesired
0x180054bbd  call    cs:__imp_RegOpenCurrentUser
0x180054bc3  test    eax, eax
0x180054bc5  jz      short loc_180054BE7
0x180054bc7  jle     short loc_180054BD1
0x180054bc9  movzx   eax, ax
0x180054bcc  or      eax, 80070000h
0x180054bd1  mov     [rsp+38h+pExceptionObject], eax
0x180054bd5  lea     rdx, _TI1J; pThrowInfo
0x180054bdc  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x180054be1  call    _CxxThrowException_0
0x180054be7  mov     rax, [rsp+38h+arg_10]
0x180054bec  mov     [rbx], rax
0x180054bef  mov     rax, rbx
0x180054bf2  add     rsp, 30h
0x180054bf6  pop     rbx
0x180054bf7  retn
```
