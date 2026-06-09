# BaseHttpListener::DecrThreadCount(void)

- ea: `0x180025d44`
- end: `0x180025dd3`
- name: `?DecrThreadCount@BaseHttpListener@@IEAAXXZ`
- size: `143`
- prototype: `void __fastcall(BaseHttpListener *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18001bfa0`
- `0x180023738`
- `0x180025ccc`
- `0x180033640`
- `0x180033a88`

## callees

- `0x180025d44`
- `0x180031018`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025dc7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180025daf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180025daf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025d54`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025d54`

## pseudocode

```c
void __fastcall BaseHttpListener::DecrThreadCount(BaseHttpListener *this)
{
  EnterCriticalSection(&g_csThreadCount);
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      131,
      WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids,
      *((unsigned int *)this + 70),
      *((_DWORD *)this + 28));
  if ( (*((_DWORD *)this + 70))-- == 1 )
    SetEvent(*((HANDLE *)this + 36));
  LeaveCriticalSection(&g_csThreadCount);
}

```

## disassembly

```asm
0x180025d44  push    rbx
0x180025d46  sub     rsp, 30h
0x180025d4a  mov     rbx, rcx
0x180025d4d  lea     rcx, ?g_csThreadCount@@3VCUCriticalSection@@A; lpCriticalSection
0x180025d54  call    cs:__imp_EnterCriticalSection
0x180025d5b  nop     dword ptr [rax+rax+00h]
0x180025d60  mov     rcx, cs:WPP_GLOBAL_Control
0x180025d67  lea     rax, WPP_GLOBAL_Control
0x180025d6e  cmp     rcx, rax
0x180025d71  jz      short loc_180025D9F
0x180025d73  test    dword ptr [rcx+1Ch], 100h
0x180025d7a  jz      short loc_180025D9F
0x180025d7c  mov     eax, [rbx+70h]
0x180025d7f  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180025d86  mov     r9d, [rbx+118h]
0x180025d8d  mov     edx, 83h
0x180025d92  mov     rcx, [rcx+10h]
0x180025d96  mov     [rsp+38h+var_18], eax
0x180025d9a  call    WPP_SF_Dd
0x180025d9f  sub     dword ptr [rbx+118h], 1
0x180025da6  jnz     short loc_180025DBB
0x180025da8  mov     rcx, [rbx+120h]; hEvent
0x180025daf  call    cs:__imp_SetEvent
0x180025db6  nop     dword ptr [rax+rax+00h]
0x180025dbb  lea     rcx, ?g_csThreadCount@@3VCUCriticalSection@@A; CUCriticalSection g_csThreadCount
0x180025dc2  add     rsp, 30h
0x180025dc6  pop     rbx
0x180025dc7  jmp     cs:__imp_LeaveCriticalSection
```
