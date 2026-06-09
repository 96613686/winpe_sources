# BaseHttpListener::DecrThreadCount(void)

- ea: `0x1800242a4`
- end: `0x180024322`
- name: `?DecrThreadCount@BaseHttpListener@@IEAAXXZ`
- size: `126`
- prototype: `void __fastcall(BaseHttpListener *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18001ac40`
- `0x180021e64`
- `0x18002422c`
- `0x180030f00`
- `0x180031280`

## callees

- `0x1800242a4`
- `0x18002edf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002431b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180024309`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180024309`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800242b4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800242b4`

## pseudocode

```c
void __fastcall BaseHttpListener::DecrThreadCount(BaseHttpListener *this)
{
  int v3; // [rsp+20h] [rbp-18h]

  EnterCriticalSection(&g_csThreadCount);
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    v3 = *((_DWORD *)this + 28);
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      131,
      WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids,
      *((unsigned int *)this + 70),
      v3);
  }
  if ( (*((_DWORD *)this + 70))-- == 1 )
    SetEvent(*((HANDLE *)this + 36));
  LeaveCriticalSection(&g_csThreadCount);
}

```

## disassembly

```asm
0x1800242a4  push    rbx
0x1800242a6  sub     rsp, 30h
0x1800242aa  mov     rbx, rcx
0x1800242ad  lea     rcx, ?g_csThreadCount@@3VCUCriticalSection@@A; lpCriticalSection
0x1800242b4  call    cs:__imp_EnterCriticalSection
0x1800242ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800242c1  lea     rax, WPP_GLOBAL_Control
0x1800242c8  cmp     rcx, rax
0x1800242cb  jz      short loc_1800242F9
0x1800242cd  test    dword ptr [rcx+1Ch], 100h
0x1800242d4  jz      short loc_1800242F9
0x1800242d6  mov     eax, [rbx+70h]
0x1800242d9  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x1800242e0  mov     r9d, [rbx+118h]
0x1800242e7  mov     edx, 83h
0x1800242ec  mov     rcx, [rcx+10h]
0x1800242f0  mov     [rsp+38h+var_18], eax
0x1800242f4  call    WPP_SF_Dd
0x1800242f9  sub     dword ptr [rbx+118h], 1
0x180024300  jnz     short loc_18002430F
0x180024302  mov     rcx, [rbx+120h]; hEvent
0x180024309  call    cs:__imp_SetEvent
0x18002430f  lea     rcx, ?g_csThreadCount@@3VCUCriticalSection@@A; CUCriticalSection g_csThreadCount
0x180024316  add     rsp, 30h
0x18002431a  pop     rbx
0x18002431b  jmp     cs:__imp_LeaveCriticalSection
```
