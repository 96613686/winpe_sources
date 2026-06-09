# CleanupListNetwork(int)

- ea: `0x180032480`
- end: `0x18003256a`
- name: `?CleanupListNetwork@@YAXH@Z`
- size: `234`
- prototype: `void __fastcall(int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002f900`

## callees

- `0x18000f350`
- `0x18000f390`
- `0x18000f6f0`
- `0x180032480`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800324b4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800324b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032541`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032541`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032500`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032500`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800324ed`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800324ed`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003255e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800324ce`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800324ce`

## pseudocode

```c
void __fastcall CleanupListNetwork()
{
  unsigned int v0; // eax
  void *v1; // rbx
  struct _SSDPNetwork *v2; // rbx
  struct _SSDPNetwork **v3; // rax
  struct _SSDPNetwork *v4; // rcx
  void *Block; // [rsp+38h] [rbp+10h] BYREF

  Block = 0;
  v0 = CleanupListNetworkForReset((void ***)&Block);
  v1 = Block;
  WaitForCallbacksToComplete((void **)Block, v0);
  if ( v1 )
    free(v1);
  while ( qword_1800452E8 != (struct _SSDPNetwork *)&qword_1800452E8 )
    Sleep(0xAu);
  DeleteCriticalSection(&stru_1800452F8);
  EnterCriticalSection(&stru_180045330);
  v2 = qword_180045320;
  while ( v2 != (struct _SSDPNetwork *)&qword_180045320 )
  {
    v3 = (struct _SSDPNetwork **)*((_QWORD *)v2 + 1);
    v4 = v2;
    v2 = *(struct _SSDPNetwork **)v2;
    *v3 = v2;
    *((_QWORD *)v2 + 1) = v3;
    FreeSSDPNetwork(v4);
  }
  LeaveCriticalSection(&stru_180045330);
  DeleteCriticalSection(&stru_180045330);
}

```

## disassembly

```asm
0x180032480  mov     [rsp+arg_0], rbx
0x180032485  push    rsi
0x180032486  sub     rsp, 20h
0x18003248a  lea     rcx, [rsp+28h+Block]; void ***
0x18003248f  mov     [rsp+28h+Block], 0
0x180032498  call    ?CleanupListNetworkForReset@@YAKPEAPEAPEAX@Z; CleanupListNetworkForReset(void * * *)
0x18003249d  mov     rbx, [rsp+28h+Block]
0x1800324a2  mov     edx, eax; unsigned int
0x1800324a4  mov     rcx, rbx; void **
0x1800324a7  call    ?WaitForCallbacksToComplete@@YAXPEAPEAXK@Z; WaitForCallbacksToComplete(void * *,ulong)
0x1800324ac  test    rbx, rbx
0x1800324af  jz      short loc_1800324C0
0x1800324b1  mov     rcx, rbx; Block
0x1800324b4  call    cs:__imp_free
0x1800324bb  nop     dword ptr [rax+rax+00h]
0x1800324c0  lea     rbx, qword_1800452E8
0x1800324c7  jmp     short loc_1800324DA
0x1800324c9  mov     ecx, 0Ah; dwMilliseconds
0x1800324ce  call    cs:__imp_Sleep
0x1800324d5  nop     dword ptr [rax+rax+00h]
0x1800324da  mov     rax, cs:qword_1800452E8
0x1800324e1  cmp     rax, rbx
0x1800324e4  jnz     short loc_1800324C9
0x1800324e6  lea     rcx, stru_1800452F8; lpCriticalSection
0x1800324ed  call    cs:__imp_DeleteCriticalSection
0x1800324f4  nop     dword ptr [rax+rax+00h]
0x1800324f9  lea     rcx, stru_180045330; lpCriticalSection
0x180032500  call    cs:__imp_EnterCriticalSection
0x180032507  nop     dword ptr [rax+rax+00h]
0x18003250c  mov     rbx, cs:qword_180045320
0x180032513  lea     rsi, qword_180045320
0x18003251a  jmp     short loc_180032535
0x18003251c  mov     rax, [rbx+8]
0x180032520  mov     rcx, rbx; struct _SSDPNetwork *
0x180032523  mov     rdx, [rbx]
0x180032526  mov     rbx, rdx
0x180032529  mov     [rax], rdx
0x18003252c  mov     [rdx+8], rax
0x180032530  call    ?FreeSSDPNetwork@@YAXPEAU_SSDPNetwork@@@Z; FreeSSDPNetwork(_SSDPNetwork *)
0x180032535  cmp     rbx, rsi
0x180032538  jnz     short loc_18003251C
0x18003253a  lea     rcx, stru_180045330; lpCriticalSection
0x180032541  call    cs:__imp_LeaveCriticalSection
0x180032548  nop     dword ptr [rax+rax+00h]
0x18003254d  lea     rcx, stru_180045330
0x180032554  mov     rbx, [rsp+28h+arg_0]
0x180032559  add     rsp, 20h
0x18003255d  pop     rsi
0x18003255e  jmp     cs:__imp_DeleteCriticalSection
```
