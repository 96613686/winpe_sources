# HDSrv::CHWEventDetectorImpl::InitMinimum(int,ushort const *)

- ea: `0x180023f30`
- end: `0x180023f96`
- name: `?InitMinimum@CHWEventDetectorImpl@HDSrv@@UEAAJHPEBG@Z`
- size: `102`
- prototype: `__int64 __fastcall(HDSrv::CHWEventDetectorImpl *__hidden this, int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001c578`
- `0x180023f30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180023f58`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180023f58`

## pseudocode

```c
__int64 __fastcall HDSrv::CHWEventDetectorImpl::InitMinimum(
        HDSrv::CHWEventDetectorImpl *this,
        int a2,
        const unsigned __int16 *a3)
{
  HANDLE v5; // rax
  XProcHelpers *v6; // rcx
  __int64 result; // rax

  if ( !a3 || !*a3 )
    return 2147942487LL;
  v5 = OpenEventW(0x100000u, 0, a3);
  *((_QWORD *)this + 2) = v5;
  if ( !v5 )
    return 2147500037LL;
  result = XProcHelpers::Initialize(v6);
  if ( (int)result >= 0 )
  {
    dword_18003E598 = a2;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180023f30  mov     [rsp+arg_0], rbx
0x180023f35  mov     [rsp+arg_8], rsi
0x180023f3a  push    rdi
0x180023f3b  sub     rsp, 20h
0x180023f3f  xor     esi, esi
0x180023f41  mov     ebx, edx
0x180023f43  mov     rdi, rcx
0x180023f46  test    r8, r8
0x180023f49  jz      short loc_180023F81
0x180023f4b  cmp     [r8], si
0x180023f4f  jz      short loc_180023F81
0x180023f51  xor     edx, edx; bInheritHandle
0x180023f53  mov     ecx, 100000h; dwDesiredAccess
0x180023f58  call    cs:__imp_OpenEventW
0x180023f5e  mov     [rdi+10h], rax
0x180023f62  test    rax, rax
0x180023f65  jz      short loc_180023F7A
0x180023f67  call    ?Initialize@XProcHelpers@@YAJXZ; XProcHelpers::Initialize(void)
0x180023f6c  test    eax, eax
0x180023f6e  js      short loc_180023F86
0x180023f70  mov     cs:dword_18003E598, ebx
0x180023f76  mov     eax, esi
0x180023f78  jmp     short loc_180023F86
0x180023f7a  mov     eax, 80004005h
0x180023f7f  jmp     short loc_180023F86
0x180023f81  mov     eax, 80070057h
0x180023f86  mov     rbx, [rsp+28h+arg_0]
0x180023f8b  mov     rsi, [rsp+28h+arg_8]
0x180023f90  add     rsp, 20h
0x180023f94  pop     rdi
0x180023f95  retn
```
