# CWcnUpnpDiscoveryListener::~CWcnUpnpDiscoveryListener(void)

- ea: `0x180042100`
- end: `0x180042224`
- name: `??1CWcnUpnpDiscoveryListener@@IEAA@XZ`
- size: `292`
- prototype: `void __fastcall(CWcnUpnpDiscoveryListener *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180042230`

## callees

- `0x1800026b4`
- `0x18000273c`
- `0x18004053c`
- `0x180042074`
- `0x180042100`
- `0x180043478`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800421be`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800421be`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004220d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004220d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18004212a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18004212a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180042134`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180042134`

## pseudocode

```c
void __fastcall CWcnUpnpDiscoveryListener::~CWcnUpnpDiscoveryListener(CWcnUpnpDiscoveryListener *this)
{
  struct _TP_WORK *v2; // rcx
  unsigned __int64 v3; // rsi
  __int64 *v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  _DWORD *v7; // rsi
  unsigned int v8; // edx
  __int64 v9; // rax
  __int64 v10; // rax
  char v11; // [rsp+30h] [rbp+8h] BYREF

  *(_QWORD *)this = &CWcnUpnpDiscoveryListener::`vftable';
  v2 = (struct _TP_WORK *)*((_QWORD *)this + 9);
  if ( v2 )
  {
    WaitForThreadpoolWorkCallbacks(v2, 1);
    CloseThreadpoolWork(*((PTP_WORK *)this + 9));
  }
  if ( *((_BYTE *)this + 80) )
    WcnUpnpReleaseGit();
  while ( *((_QWORD *)this + 16) )
  {
    v3 = *((_QWORD *)this + 15);
    if ( this == (CWcnUpnpDiscoveryListener *)-96LL )
    {
      std::_Lockit::_Lockit((std::_Lockit *)&v11, 3);
      std::_Lockit::~_Lockit((std::_Lockit *)&v11);
      v4 = 0;
    }
    else
    {
      v4 = (__int64 *)*((_QWORD *)this + 12);
    }
    if ( v4 )
      v5 = *v4;
    else
      v5 = 0;
    v6 = (v3 >> 1) & (*(_QWORD *)(v5 + 16) - 1LL);
    v7 = *(_DWORD **)(*(_QWORD *)(*(_QWORD *)(v5 + 8) + 8 * v6) + 8 * (v3 & 1));
    if ( v7 )
    {
      v8 = v7[5];
      if ( v8 )
        CWcnUpnpGit::RemoveItem((CWcnUpnpGit *)v6, v8);
      operator delete(v7);
    }
    v9 = *((_QWORD *)this + 16);
    if ( v9 )
    {
      v10 = v9 - 1;
      *((_QWORD *)this + 16) = v10;
      if ( v10 )
        ++*((_QWORD *)this + 15);
      else
        *((_QWORD *)this + 15) = 0;
    }
  }
  std::deque<CWcnUpnpDiscoveryListener::tagWCN_CALLBACK_DATA *>::~deque<CWcnUpnpDiscoveryListener::tagWCN_CALLBACK_DATA *>((char *)this + 96);
  if ( *((_BYTE *)this + 56) )
  {
    *((_BYTE *)this + 56) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  }
}

```

## disassembly

```asm
0x180042100  mov     [rsp+arg_8], rbx
0x180042105  mov     [rsp+arg_10], rsi
0x18004210a  push    rdi
0x18004210b  sub     rsp, 20h
0x18004210f  mov     rbx, rcx
0x180042112  lea     rax, ??_7CWcnUpnpDiscoveryListener@@6B@; const CWcnUpnpDiscoveryListener::`vftable'
0x180042119  mov     [rcx], rax
0x18004211c  mov     rcx, [rcx+48h]; pwk
0x180042120  test    rcx, rcx
0x180042123  jz      short loc_18004213A
0x180042125  mov     edx, 1; fCancelPendingCallbacks
0x18004212a  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180042130  mov     rcx, [rbx+48h]; pwk
0x180042134  call    cs:__imp_CloseThreadpoolWork
0x18004213a  cmp     byte ptr [rbx+50h], 0
0x18004213e  jz      short loc_180042145
0x180042140  call    ?WcnUpnpReleaseGit@@YAXXZ; WcnUpnpReleaseGit(void)
0x180042145  lea     rdi, [rbx+60h]
0x180042149  cmp     qword ptr [rbx+80h], 0
0x180042151  jz      loc_1800421F7
0x180042157  mov     rsi, [rdi+18h]
0x18004215b  test    rdi, rdi
0x18004215e  jnz     short loc_18004217B
0x180042160  lea     edx, [rdi+3]; int
0x180042163  lea     rcx, [rsp+28h+arg_0]; this
0x180042168  call    ??0_Lockit@std@@QEAA@H@Z; std::_Lockit::_Lockit(int)
0x18004216d  lea     rcx, [rsp+28h+arg_0]; this
0x180042172  call    ??1_Lockit@std@@QEAA@XZ; std::_Lockit::~_Lockit(void)
0x180042177  xor     eax, eax
0x180042179  jmp     short loc_18004217E
0x18004217b  mov     rax, [rdi]
0x18004217e  test    rax, rax
0x180042181  jnz     short loc_180042187
0x180042183  xor     edx, edx
0x180042185  jmp     short loc_18004218A
0x180042187  mov     rdx, [rax]
0x18004218a  mov     rcx, [rdx+10h]
0x18004218e  dec     rcx
0x180042191  mov     rax, rsi
0x180042194  shr     rax, 1
0x180042197  and     rcx, rax; this
0x18004219a  mov     rax, [rdx+8]
0x18004219e  and     esi, 1
0x1800421a1  mov     rax, [rax+rcx*8]
0x1800421a5  mov     rsi, [rax+rsi*8]
0x1800421a9  test    rsi, rsi
0x1800421ac  jz      short loc_1800421C4
0x1800421ae  mov     edx, [rsi+14h]; unsigned int
0x1800421b1  test    edx, edx
0x1800421b3  jz      short loc_1800421BB
0x1800421b5  call    ?RemoveItem@CWcnUpnpGit@@QEAAXK@Z; CWcnUpnpGit::RemoveItem(ulong)
0x1800421ba  nop
0x1800421bb  mov     rcx, rsi
0x1800421be  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800421c4  mov     rax, [rbx+80h]
0x1800421cb  test    rax, rax
0x1800421ce  jz      loc_180042149
0x1800421d4  sub     rax, 1
0x1800421d8  mov     [rbx+80h], rax
0x1800421df  jnz     short loc_1800421EE
0x1800421e1  mov     qword ptr [rbx+78h], 0
0x1800421e9  jmp     loc_180042149
0x1800421ee  inc     qword ptr [rbx+78h]
0x1800421f2  jmp     loc_180042149
0x1800421f7  mov     rcx, rdi
0x1800421fa  call    ??1?$deque@PEAUtagWCN_CALLBACK_DATA@CWcnUpnpDiscoveryListener@@V?$allocator@PEAUtagWCN_CALLBACK_DATA@CWcnUpnpDiscoveryListener@@@std@@@std@@QEAA@XZ; std::deque<CWcnUpnpDiscoveryListener::tagWCN_CALLBACK_DATA *>::~deque<CWcnUpnpDiscoveryListener::tagWCN_CALLBACK_DATA *>(void)
0x1800421ff  lea     rcx, [rbx+10h]; lpCriticalSection
0x180042203  cmp     byte ptr [rcx+28h], 0
0x180042207  jz      short loc_180042214
0x180042209  mov     byte ptr [rcx+28h], 0
0x18004220d  call    cs:__imp_DeleteCriticalSection
0x180042213  nop
0x180042214  mov     rbx, [rsp+28h+arg_8]
0x180042219  mov     rsi, [rsp+28h+arg_10]
0x18004221e  add     rsp, 20h
0x180042222  pop     rdi
0x180042223  retn
```
