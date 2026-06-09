# CUpdateCleanup::UploadSqmData(void)

- ea: `0x180003710`
- end: `0x18000378f`
- name: `?UploadSqmData@CUpdateCleanup@@MEAAXXZ`
- size: `127`
- prototype: `void __fastcall(CUpdateCleanup *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, installer_update`

## import_xrefs

- `ntdll!WinSqmStartSession` at `0x180003728`
- `ntdll!WinSqmStartSession` at `0x180003728`
- `ntdll!WinSqmSetDWORD` at `0x180003744`
- `ntdll!WinSqmSetDWORD` at `0x180003776`
- `ntdll!WinSqmSetDWORD` at `0x180003744`
- `ntdll!WinSqmSetDWORD` at `0x180003776`
- `ntdll!WinSqmSetDWORD64` at `0x18000375d`
- `ntdll!WinSqmSetDWORD64` at `0x18000375d`
- `ntdll!WinSqmEndSession` at `0x180003788`

## pseudocode

```c
void __fastcall CUpdateCleanup::UploadSqmData(CUpdateCleanup *this)
{
  __int64 started; // rax
  __int64 v3; // r8

  started = WinSqmStartSession(qword_180007FE0, 101457988, 0);
  v3 = *((unsigned int *)this + 152);
  *((_QWORD *)this + 74) = started;
  WinSqmSetDWORD(started, 10958, v3);
  WinSqmSetDWORD64(*((_QWORD *)this + 74), 10957, *((_QWORD *)this + 75));
  WinSqmSetDWORD(*((_QWORD *)this + 74), 10959, *((unsigned int *)this + 136));
  WinSqmEndSession(*((_QWORD *)this + 74));
}

```

## disassembly

```asm
0x180003710  push    rbx
0x180003712  sub     rsp, 20h
0x180003716  mov     rbx, rcx
0x180003719  xor     r8d, r8d
0x18000371c  lea     rcx, qword_180007FE0
0x180003723  mov     edx, 60C2044h
0x180003728  call    cs:__imp_WinSqmStartSession
0x18000372e  mov     r8d, [rbx+260h]
0x180003735  mov     edx, 2ACEh
0x18000373a  mov     rcx, rax
0x18000373d  mov     [rbx+250h], rax
0x180003744  call    cs:__imp_WinSqmSetDWORD
0x18000374a  mov     r8, [rbx+258h]
0x180003751  mov     edx, 2ACDh
0x180003756  mov     rcx, [rbx+250h]
0x18000375d  call    cs:__imp_WinSqmSetDWORD64
0x180003763  mov     r8d, [rbx+220h]
0x18000376a  mov     edx, 2ACFh
0x18000376f  mov     rcx, [rbx+250h]
0x180003776  call    cs:__imp_WinSqmSetDWORD
0x18000377c  mov     rcx, [rbx+250h]
0x180003783  add     rsp, 20h
0x180003787  pop     rbx
0x180003788  jmp     cs:__imp_WinSqmEndSession
```
