# CAPIDispatchSync::CAPIDispatchSync(void)

- ea: `0x180003ee0`
- end: `0x180003f89`
- name: `??0CAPIDispatchSync@@QEAA@XZ`
- size: `169`
- prototype: `CAPIDispatchSync *__fastcall(CAPIDispatchSync *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1800035e0`

## callees

- `0x180003ee0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180003f12`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180003f12`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180003f38`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180003f4e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180003f62`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180003f76`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180003f38`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180003f4e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180003f62`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180003f76`

## pseudocode

```c
CAPIDispatchSync *__fastcall CAPIDispatchSync::CAPIDispatchSync(CAPIDispatchSync *this)
{
  *((_DWORD *)this + 10) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)this, 0) )
  {
    *(_OWORD *)this = 0;
    *((_OWORD *)this + 1) = 0;
    *((_QWORD *)this + 4) = 0;
  }
  *((_QWORD *)this + 6) = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 7) = CreateEventW(0, 1, 1, 0);
  *((_QWORD *)this + 8) = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 9) = CreateEventW(0, 0, 0, 0);
  return this;
}

```

## disassembly

```asm
0x180003ee0  push    rbx
0x180003ee2  sub     rsp, 20h
0x180003ee6  xor     edx, edx; dwSpinCount
0x180003ee8  mov     dword ptr [rcx+28h], 0
0x180003eef  mov     rbx, rcx
0x180003ef2  mov     qword ptr [rcx+30h], 0
0x180003efa  mov     qword ptr [rcx+38h], 0
0x180003f02  mov     qword ptr [rcx+40h], 0
0x180003f0a  mov     qword ptr [rcx+48h], 0
0x180003f12  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180003f18  test    eax, eax
0x180003f1a  jnz     short loc_180003F2C
0x180003f1c  xorps   xmm0, xmm0
0x180003f1f  xor     eax, eax
0x180003f21  movups  xmmword ptr [rbx], xmm0
0x180003f24  movups  xmmword ptr [rbx+10h], xmm0
0x180003f28  mov     [rbx+20h], rax
0x180003f2c  xor     r9d, r9d; lpName
0x180003f2f  xor     r8d, r8d; bInitialState
0x180003f32  xor     ecx, ecx; lpEventAttributes
0x180003f34  lea     edx, [r9+1]; bManualReset
0x180003f38  call    cs:__imp_CreateEventW
0x180003f3e  xor     r9d, r9d; lpName
0x180003f41  xor     ecx, ecx; lpEventAttributes
0x180003f43  mov     [rbx+30h], rax
0x180003f47  lea     edx, [r9+1]; bManualReset
0x180003f4b  mov     r8d, edx; bInitialState
0x180003f4e  call    cs:__imp_CreateEventW
0x180003f54  xor     r9d, r9d; lpName
0x180003f57  xor     r8d, r8d; bInitialState
0x180003f5a  xor     edx, edx; bManualReset
0x180003f5c  mov     [rbx+38h], rax
0x180003f60  xor     ecx, ecx; lpEventAttributes
0x180003f62  call    cs:__imp_CreateEventW
0x180003f68  xor     r9d, r9d; lpName
0x180003f6b  xor     r8d, r8d; bInitialState
0x180003f6e  xor     edx, edx; bManualReset
0x180003f70  mov     [rbx+40h], rax
0x180003f74  xor     ecx, ecx; lpEventAttributes
0x180003f76  call    cs:__imp_CreateEventW
0x180003f7c  mov     [rbx+48h], rax
0x180003f80  mov     rax, rbx
0x180003f83  add     rsp, 20h
0x180003f87  pop     rbx
0x180003f88  retn
```
