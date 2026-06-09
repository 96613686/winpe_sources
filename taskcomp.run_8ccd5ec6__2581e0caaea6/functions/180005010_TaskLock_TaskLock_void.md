# TaskLock::~TaskLock(void)

- ea: `0x180005010`
- end: `0x18000508e`
- name: `??1TaskLock@@QEAA@XZ`
- size: `126`
- prototype: `void __fastcall(TaskLock *__hidden this)`
- caller_count: `10`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180004a40`
- `0x1800111e0`
- `0x180011600`
- `0x1800130c0`
- `0x180013a80`
- `0x180016040`
- `0x180030ab3`
- `0x18003166e`
- `0x180031833`
- `0x1800318f6`

## callees

- `0x180005010`
- `0x18000d128`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18000502c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18000502c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000503f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000503f`

## pseudocode

```c
void __fastcall TaskLock::~TaskLock(TaskLock *this)
{
  void *v2; // rcx

  v2 = (void *)*((_QWORD *)this + 65);
  if ( v2 )
  {
    ReleaseSemaphore(v2, 1, 0);
    CloseHandle(*((HANDLE *)this + 65));
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_074089b8976f3c6b31fe3e9d061e666a_Traceguids, this);
  }
  *(_WORD *)this = 0;
}

```

## disassembly

```asm
0x180005010  push    rbx
0x180005012  sub     rsp, 20h
0x180005016  mov     rbx, rcx
0x180005019  mov     rcx, [rcx+208h]; hSemaphore
0x180005020  test    rcx, rcx
0x180005023  jz      short loc_18000504B
0x180005025  xor     r8d, r8d; lpPreviousCount
0x180005028  lea     edx, [r8+1]; lReleaseCount
0x18000502c  call    cs:__imp_ReleaseSemaphore
0x180005033  nop     dword ptr [rax+rax+00h]
0x180005038  mov     rcx, [rbx+208h]; hObject
0x18000503f  call    cs:__imp_CloseHandle
0x180005046  nop     dword ptr [rax+rax+00h]
0x18000504b  mov     rcx, cs:WPP_GLOBAL_Control
0x180005052  lea     rax, WPP_GLOBAL_Control
0x180005059  cmp     rcx, rax
0x18000505c  jz      short loc_180005082
0x18000505e  test    byte ptr [rcx+1Ch], 2
0x180005062  jz      short loc_180005082
0x180005064  cmp     byte ptr [rcx+19h], 4
0x180005068  jb      short loc_180005082
0x18000506a  mov     rcx, [rcx+10h]
0x18000506e  lea     r8, WPP_074089b8976f3c6b31fe3e9d061e666a_Traceguids
0x180005075  mov     edx, 0Dh
0x18000507a  mov     r9, rbx
0x18000507d  call    WPP_SF_S
0x180005082  xor     eax, eax
0x180005084  mov     [rbx], ax
0x180005087  add     rsp, 20h
0x18000508b  pop     rbx
0x18000508c  retn
```
