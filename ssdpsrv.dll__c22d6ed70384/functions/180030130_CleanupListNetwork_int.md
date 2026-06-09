# CleanupListNetwork(int)

- ea: `0x180030130`
- end: `0x1800301f7`
- name: `?CleanupListNetwork@@YAXH@Z`
- size: `199`
- prototype: `void __fastcall()`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002d870`

## callees

- `0x18000df80`
- `0x18000dfb0`
- `0x18000e2bc`
- `0x180030130`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180030164`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180030164`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800301d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800301d9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003019e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003019e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180030191`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180030191`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800301f0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180030178`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180030178`

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
  while ( ::Block != (struct _SSDPNetwork *)&::Block )
    Sleep(0xAu);
  DeleteCriticalSection(&stru_180042200);
  EnterCriticalSection(&stru_180042240);
  v2 = qword_180042230;
  while ( v2 != (struct _SSDPNetwork *)&qword_180042230 )
  {
    v3 = (struct _SSDPNetwork **)*((_QWORD *)v2 + 1);
    v4 = v2;
    v2 = *(struct _SSDPNetwork **)v2;
    *v3 = v2;
    *((_QWORD *)v2 + 1) = v3;
    FreeSSDPNetwork(v4);
  }
  LeaveCriticalSection(&stru_180042240);
  DeleteCriticalSection(&stru_180042240);
}

```

## disassembly

```asm
0x180030130  mov     [rsp+arg_0], rbx
0x180030135  push    rsi
0x180030136  sub     rsp, 20h
0x18003013a  lea     rcx, [rsp+28h+Block]; void ***
0x18003013f  mov     [rsp+28h+Block], 0
0x180030148  call    ?CleanupListNetworkForReset@@YAKPEAPEAPEAX@Z; CleanupListNetworkForReset(void * * *)
0x18003014d  mov     rbx, [rsp+28h+Block]
0x180030152  mov     edx, eax; unsigned int
0x180030154  mov     rcx, rbx; void **
0x180030157  call    ?WaitForCallbacksToComplete@@YAXPEAPEAXK@Z; WaitForCallbacksToComplete(void * *,ulong)
0x18003015c  test    rbx, rbx
0x18003015f  jz      short loc_18003016A
0x180030161  mov     rcx, rbx; Block
0x180030164  call    cs:__imp_free
0x18003016a  lea     rbx, Block
0x180030171  jmp     short loc_18003017E
0x180030173  mov     ecx, 0Ah; dwMilliseconds
0x180030178  call    cs:__imp_Sleep
0x18003017e  mov     rax, cs:Block
0x180030185  cmp     rax, rbx
0x180030188  jnz     short loc_180030173
0x18003018a  lea     rcx, stru_180042200; lpCriticalSection
0x180030191  call    cs:__imp_DeleteCriticalSection
0x180030197  lea     rcx, stru_180042240; lpCriticalSection
0x18003019e  call    cs:__imp_EnterCriticalSection
0x1800301a4  mov     rbx, cs:qword_180042230
0x1800301ab  lea     rsi, qword_180042230
0x1800301b2  jmp     short loc_1800301CD
0x1800301b4  mov     rax, [rbx+8]
0x1800301b8  mov     rcx, rbx; struct _SSDPNetwork *
0x1800301bb  mov     rdx, [rbx]
0x1800301be  mov     rbx, rdx
0x1800301c1  mov     [rax], rdx
0x1800301c4  mov     [rdx+8], rax
0x1800301c8  call    ?FreeSSDPNetwork@@YAXPEAU_SSDPNetwork@@@Z; FreeSSDPNetwork(_SSDPNetwork *)
0x1800301cd  cmp     rbx, rsi
0x1800301d0  jnz     short loc_1800301B4
0x1800301d2  lea     rcx, stru_180042240; lpCriticalSection
0x1800301d9  call    cs:__imp_LeaveCriticalSection
0x1800301df  lea     rcx, stru_180042240
0x1800301e6  mov     rbx, [rsp+28h+arg_0]
0x1800301eb  add     rsp, 20h
0x1800301ef  pop     rsi
0x1800301f0  jmp     cs:__imp_DeleteCriticalSection
```
