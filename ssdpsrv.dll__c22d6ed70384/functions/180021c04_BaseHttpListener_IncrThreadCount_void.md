# BaseHttpListener::IncrThreadCount(void)

- ea: `0x180021c04`
- end: `0x180021c88`
- name: `?IncrThreadCount@BaseHttpListener@@IEAAXXZ`
- size: `132`
- prototype: `void __fastcall(BaseHttpListener *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18001ac40`
- `0x18001f3e0`
- `0x180031280`

## callees

- `0x180021c04`
- `0x18002edf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021c81`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021c14`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021c14`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180021c6f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180021c6f`

## pseudocode

```c
void __fastcall BaseHttpListener::IncrThreadCount(BaseHttpListener *this)
{
  int v2; // [rsp+20h] [rbp-18h]

  EnterCriticalSection(&g_csThreadCount);
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    v2 = *((_DWORD *)this + 28);
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      130,
      WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids,
      *((unsigned int *)this + 70),
      v2);
  }
  if ( ++*((_DWORD *)this + 70) == 1 )
    ResetEvent(*((HANDLE *)this + 36));
  LeaveCriticalSection(&g_csThreadCount);
}

```

## disassembly

```asm
0x180021c04  push    rbx
0x180021c06  sub     rsp, 30h
0x180021c0a  mov     rbx, rcx
0x180021c0d  lea     rcx, ?g_csThreadCount@@3VCUCriticalSection@@A; lpCriticalSection
0x180021c14  call    cs:__imp_EnterCriticalSection
0x180021c1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180021c21  lea     rax, WPP_GLOBAL_Control
0x180021c28  cmp     rcx, rax
0x180021c2b  jz      short loc_180021C59
0x180021c2d  test    dword ptr [rcx+1Ch], 100h
0x180021c34  jz      short loc_180021C59
0x180021c36  mov     eax, [rbx+70h]
0x180021c39  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180021c40  mov     r9d, [rbx+118h]
0x180021c47  mov     edx, 82h
0x180021c4c  mov     rcx, [rcx+10h]
0x180021c50  mov     [rsp+38h+var_18], eax
0x180021c54  call    WPP_SF_Dd
0x180021c59  inc     dword ptr [rbx+118h]
0x180021c5f  cmp     dword ptr [rbx+118h], 1
0x180021c66  jnz     short loc_180021C75
0x180021c68  mov     rcx, [rbx+120h]; hEvent
0x180021c6f  call    cs:__imp_ResetEvent
0x180021c75  lea     rcx, ?g_csThreadCount@@3VCUCriticalSection@@A; CUCriticalSection g_csThreadCount
0x180021c7c  add     rsp, 30h
0x180021c80  pop     rbx
0x180021c81  jmp     cs:__imp_LeaveCriticalSection
```
