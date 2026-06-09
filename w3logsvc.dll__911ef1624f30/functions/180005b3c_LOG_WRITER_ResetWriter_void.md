# LOG_WRITER::ResetWriter(void)

- ea: `0x180005b3c`
- end: `0x180005bcc`
- name: `?ResetWriter@LOG_WRITER@@AEAAXXZ`
- size: `144`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004fe4`
- `0x180005bd4`

## callees

- `0x180005b3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005bc5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005b53`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005b53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b66`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b66`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180005bb2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180005bb2`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180005baa`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180005baa`

## pseudocode

```c
void __fastcall LOG_WRITER::ResetWriter(struct _RTL_CRITICAL_SECTION *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  void *SpinCount; // rcx
  _WORD *v4; // rcx
  struct _SYSTEMTIME *p_LockCount; // rcx
  __int64 v6; // rax

  v1 = this + 17;
  EnterCriticalSection(this + 17);
  SpinCount = (void *)this[15].SpinCount;
  if ( SpinCount != (void *)-1LL )
  {
    CloseHandle(SpinCount);
    this[15].SpinCount = -1;
  }
  *(_WORD *)this[2].LockSemaphore = 0;
  v4 = *(_WORD **)&this[1].LockCount;
  LODWORD(this[3].DebugInfo) = 0;
  *v4 = 0;
  p_LockCount = (struct _SYSTEMTIME *)&this[16].LockCount;
  LODWORD(this[1].LockSemaphore) = 0;
  v6 = *(_QWORD *)&this->LockCount;
  this[16].DebugInfo = 0;
  if ( v6 && *(_DWORD *)(v6 + 4) == 1 )
    GetLocalTime(p_LockCount);
  else
    GetSystemTime(p_LockCount);
  LeaveCriticalSection(v1);
}

```

## disassembly

```asm
0x180005b3c  mov     [rsp+arg_0], rbx
0x180005b41  push    rdi
0x180005b42  sub     rsp, 20h
0x180005b46  lea     rdi, [rcx+2A8h]
0x180005b4d  mov     rbx, rcx
0x180005b50  mov     rcx, rdi; lpCriticalSection
0x180005b53  call    cs:__imp_EnterCriticalSection
0x180005b59  mov     rcx, [rbx+278h]; hObject
0x180005b60  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180005b64  jz      short loc_180005B77
0x180005b66  call    cs:__imp_CloseHandle
0x180005b6c  mov     qword ptr [rbx+278h], 0FFFFFFFFFFFFFFFFh
0x180005b77  mov     rcx, [rbx+68h]
0x180005b7b  xor     edx, edx
0x180005b7d  mov     [rcx], dx
0x180005b80  mov     rcx, [rbx+30h]
0x180005b84  mov     [rbx+78h], edx
0x180005b87  mov     [rcx], dx
0x180005b8a  lea     rcx, [rbx+288h]; lpSystemTime
0x180005b91  mov     [rbx+40h], edx
0x180005b94  mov     rax, [rbx+8]
0x180005b98  mov     [rbx+280h], rdx
0x180005b9f  test    rax, rax
0x180005ba2  jz      short loc_180005BB2
0x180005ba4  cmp     dword ptr [rax+4], 1
0x180005ba8  jnz     short loc_180005BB2
0x180005baa  call    cs:__imp_GetLocalTime
0x180005bb0  jmp     short loc_180005BB8
0x180005bb2  call    cs:__imp_GetSystemTime
0x180005bb8  mov     rcx, rdi
0x180005bbb  mov     rbx, [rsp+28h+arg_0]
0x180005bc0  add     rsp, 20h
0x180005bc4  pop     rdi
0x180005bc5  jmp     cs:__imp_LeaveCriticalSection
```
