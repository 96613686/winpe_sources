# TaskLock::~TaskLock(void)

- ea: `0x180004da4`
- end: `0x180004e15`
- name: `??1TaskLock@@QEAA@XZ`
- size: `113`
- prototype: `void __fastcall(TaskLock *__hidden this)`
- caller_count: `10`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180004820`
- `0x180010750`
- `0x180010bd0`
- `0x180012560`
- `0x180012ea0`
- `0x180015280`
- `0x18002e963`
- `0x18002f51d`
- `0x18002f6e2`
- `0x18002f7a5`

## callees

- `0x180004da4`
- `0x18000c8f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x180004dc0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x180004dc0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004dcd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004dcd`

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
0x180004da4  push    rbx
0x180004da6  sub     rsp, 20h
0x180004daa  mov     rbx, rcx
0x180004dad  mov     rcx, [rcx+208h]; hSemaphore
0x180004db4  test    rcx, rcx
0x180004db7  jz      short loc_180004DD3
0x180004db9  xor     r8d, r8d; lpPreviousCount
0x180004dbc  lea     edx, [r8+1]; lReleaseCount
0x180004dc0  call    cs:__imp_ReleaseSemaphore
0x180004dc6  mov     rcx, [rbx+208h]; hObject
0x180004dcd  call    cs:__imp_CloseHandle
0x180004dd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180004dda  lea     rax, WPP_GLOBAL_Control
0x180004de1  cmp     rcx, rax
0x180004de4  jz      short loc_180004E0A
0x180004de6  test    byte ptr [rcx+1Ch], 2
0x180004dea  jz      short loc_180004E0A
0x180004dec  cmp     byte ptr [rcx+19h], 4
0x180004df0  jb      short loc_180004E0A
0x180004df2  mov     rcx, [rcx+10h]
0x180004df6  lea     r8, WPP_074089b8976f3c6b31fe3e9d061e666a_Traceguids
0x180004dfd  mov     edx, 0Dh
0x180004e02  mov     r9, rbx
0x180004e05  call    WPP_SF_S
0x180004e0a  xor     eax, eax
0x180004e0c  mov     [rbx], ax
0x180004e0f  add     rsp, 20h
0x180004e13  pop     rbx
0x180004e14  retn
```
