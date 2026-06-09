# BaseHttpListener::IncrThreadCount(void)

- ea: `0x1800234d8`
- end: `0x18002356d`
- name: `?IncrThreadCount@BaseHttpListener@@IEAAXXZ`
- size: `149`
- prototype: `void __fastcall(BaseHttpListener *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18001bfa0`
- `0x180020bac`
- `0x180033a88`

## callees

- `0x1800234d8`
- `0x180031018`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023561`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800234e8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800234e8`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180023549`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180023549`

## pseudocode

```c
void __fastcall BaseHttpListener::IncrThreadCount(BaseHttpListener *this)
{
  EnterCriticalSection(&g_csThreadCount);
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      130,
      WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids,
      *((unsigned int *)this + 70),
      *((_DWORD *)this + 28));
  if ( ++*((_DWORD *)this + 70) == 1 )
    ResetEvent(*((HANDLE *)this + 36));
  LeaveCriticalSection(&g_csThreadCount);
}

```

## disassembly

```asm
0x1800234d8  push    rbx
0x1800234da  sub     rsp, 30h
0x1800234de  mov     rbx, rcx
0x1800234e1  lea     rcx, ?g_csThreadCount@@3VCUCriticalSection@@A; lpCriticalSection
0x1800234e8  call    cs:__imp_EnterCriticalSection
0x1800234ef  nop     dword ptr [rax+rax+00h]
0x1800234f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800234fb  lea     rax, WPP_GLOBAL_Control
0x180023502  cmp     rcx, rax
0x180023505  jz      short loc_180023533
0x180023507  test    dword ptr [rcx+1Ch], 100h
0x18002350e  jz      short loc_180023533
0x180023510  mov     eax, [rbx+70h]
0x180023513  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18002351a  mov     r9d, [rbx+118h]
0x180023521  mov     edx, 82h
0x180023526  mov     rcx, [rcx+10h]
0x18002352a  mov     [rsp+38h+var_18], eax
0x18002352e  call    WPP_SF_Dd
0x180023533  inc     dword ptr [rbx+118h]
0x180023539  cmp     dword ptr [rbx+118h], 1
0x180023540  jnz     short loc_180023555
0x180023542  mov     rcx, [rbx+120h]; hEvent
0x180023549  call    cs:__imp_ResetEvent
0x180023550  nop     dword ptr [rax+rax+00h]
0x180023555  lea     rcx, ?g_csThreadCount@@3VCUCriticalSection@@A; CUCriticalSection g_csThreadCount
0x18002355c  add     rsp, 30h
0x180023560  pop     rbx
0x180023561  jmp     cs:__imp_LeaveCriticalSection
```
