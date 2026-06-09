# IOCompletionPortThreadPool::StartCompletionPorts(void)

- ea: `0x1005b0720`
- end: `0x1005b09ec`
- name: `?StartCompletionPorts@IOCompletionPortThreadPool@@QEAAJXZ`
- size: `716`
- prototype: `__int64 __fastcall(IOCompletionPortThreadPool *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x100403070`
- `0x100410c70`
- `0x1004208d0`
- `0x1005b0720`
- `0x1005b1fc0`

## import_xrefs

- `KERNEL32!CreateIoCompletionPort` at `0x1005b077e`
- `KERNEL32!CreateIoCompletionPort` at `0x1005b077e`
- `KERNEL32!GetLastError` at `0x1005b078d`
- `KERNEL32!GetLastError` at `0x1005b078d`

## string_xrefs

- `0x1005b0802`: `Sql\Common\src\IOCompletionPortThreadPool.cpp`
- `0x1005b07cd`: `"Sql\\Common\\src\\IOCompletionPortThreadPool.cpp"`
- `0x1005b08cf`: `"Sql\\Common\\src\\IOCompletionPortThreadPool.cpp"`
- `0x1005b0963`: `"Sql\\Common\\src\\IOCompletionPortThreadPool.cpp"`
- `0x1005b07d4`: `nullptr == m_threadPool`

## pseudocode

```c
signed int __fastcall IOCompletionPortThreadPool::StartCompletionPorts(IOCompletionPortThreadPool *this)
{
  HANDLE IoCompletionPort; // rax
  signed int result; // eax
  unsigned __int64 v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // rax
  _QWORD *v7; // rcx
  unsigned int v8; // esi
  __int64 v9; // rbp
  __int64 v10; // rdx
  char *v11; // rbx
  int v12; // [rsp+20h] [rbp-A8h]
  _BYTE v13[80]; // [rsp+40h] [rbp-88h] BYREF

  if ( *((_QWORD *)this + 1) || !*((_QWORD *)this + 2) || (unsigned int)(*(_DWORD *)this - 1) > 0xFFF )
    return -2147024809;
  IoCompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, *((_DWORD *)this + 1));
  *((_QWORD *)this + 1) = IoCompletionPort;
  if ( IoCompletionPort )
  {
    if ( *((_QWORD *)this + 3) )
      utassert_fail(1u, "nullptr == m_threadPool", "\"Sql\\\\Common\\\\src\\\\IOCompletionPortThreadPool.cpp\"", 314, 0);
    v4 = *(unsigned int *)this;
    v5 = 56 * v4;
    if ( !is_mul_ok(v4, 0x38u) )
      v5 = -1;
    if ( v5 == -1
      || (LOBYTE(v12) = 6,
          (v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, const char *, __int64, int))(**((_QWORD **)this + 2) + 80LL))(
                  *((_QWORD *)this + 2),
                  v5,
                  "Sql\\Common\\src\\IOCompletionPortThreadPool.cpp",
                  316,
                  v12)) == 0) )
    {
      *((_QWORD *)this + 3) = 0;
      return -2147024882;
    }
    if ( v4 )
    {
      v7 = (_QWORD *)(v6 + 16);
      do
      {
        *(v7 - 2) = 0;
        *((_BYTE *)v7 - 8) = 0;
        *v7 = 0;
        v7[1] = 0;
        v7[2] = 0;
        v7[3] = 0;
        v7[4] = 0;
        v7 += 7;
        --v4;
      }
      while ( v4 );
    }
    v8 = 0;
    *((_QWORD *)this + 3) = v6;
    if ( !*(_DWORD *)this )
      return 0;
    while ( 1 )
    {
      v9 = qword_100714178[(unsigned __int16)(v8 % *(_DWORD *)&SOS_OS_NumberOfNodeInfos)];
      if ( !v9 )
        goto LABEL_20;
      if ( (*(_BYTE *)(v9 + 1568) & 0x10) != 0 )
        break;
LABEL_21:
      v10 = 56LL * v8;
      *(_QWORD *)(*((_QWORD *)this + 3) + v10 + 40) = *((_QWORD *)this + 1);
      *(_QWORD *)(*((_QWORD *)this + 3) + v10 + 24) = v9;
      *(_QWORD *)(*((_QWORD *)this + 3) + v10 + 48) = this;
      v11 = (char *)(v10 + *((_QWORD *)this + 3));
      SOS_Task::Param::Init(
        (SOS_Task::Param *)v13,
        0x92u,
        (struct SOS_ResourceGroup *)qword_100716558,
        0xFFFFFFFFFFFFFFFFuLL,
        (void *(*)(void *))IOCompletionPortThreadPool::ListenOnIOCompletionPortEntryPoint,
        v11,
        0);
      if ( (unsigned int)SOS_Node::EnqueueTaskDirectInternal(v9, v13, 0, v11 + 32, 0) )
        utassert_fail(1u, "SOS_OK == result", "\"Sql\\\\Common\\\\src\\\\IOCompletionPortThreadPool.cpp\"", 337, 0);
      if ( ++v8 >= *(_DWORD *)this )
        return 0;
    }
    v9 = 0;
LABEL_20:
    utassert_fail(1u, "node", "\"Sql\\\\Common\\\\src\\\\IOCompletionPortThreadPool.cpp\"", 326, 0);
    goto LABEL_21;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1005b0720  push    rdi
0x1005b0722  sub     rsp, 0C0h
0x1005b0729  mov     rax, cs:__security_cookie
0x1005b0730  xor     rax, rsp
0x1005b0733  mov     [rsp+0C8h+var_38], rax
0x1005b073b  cmp     qword ptr [rcx+8], 0
0x1005b0740  mov     rdi, rcx
0x1005b0743  jnz     loc_1005B09E4
0x1005b0749  cmp     qword ptr [rcx+10h], 0
0x1005b074e  jz      loc_1005B09E4
0x1005b0754  mov     eax, [rcx]
0x1005b0756  dec     eax
0x1005b0758  cmp     eax, 0FFFh
0x1005b075d  ja      loc_1005B09E4
0x1005b0763  mov     r9d, [rcx+4]; NumberOfConcurrentThreads
0x1005b0767  xor     r8d, r8d; CompletionKey
0x1005b076a  mov     [rsp+0C8h+var_28], r15
0x1005b0772  xor     edx, edx; ExistingCompletionPort
0x1005b0774  mov     r15, 0FFFFFFFFFFFFFFFFh
0x1005b077b  mov     rcx, r15; FileHandle
0x1005b077e  call    cs:__imp_CreateIoCompletionPort
0x1005b0784  mov     [rdi+8], rax
0x1005b0788  test    rax, rax
0x1005b078b  jnz     short loc_1005B07A9
0x1005b078d  call    cs:__imp_GetLastError
0x1005b0793  test    eax, eax
0x1005b0795  jle     loc_1005B09B7
0x1005b079b  movzx   eax, ax
0x1005b079e  or      eax, 80070000h
0x1005b07a3  jmp     loc_1005B09B7
0x1005b07a9  mov     [rsp+0C8h+arg_8], rbx
0x1005b07b1  mov     [rsp+0C8h+var_20], r14
0x1005b07b9  xor     r14d, r14d
0x1005b07bc  cmp     [rdi+18h], r14
0x1005b07c0  jz      short loc_1005B07E4
0x1005b07c2  mov     r9d, 13Ah; int
0x1005b07c8  mov     [rsp+0C8h+var_A8], r14; Format
0x1005b07cd  lea     r8, aSqlCommonSrcIo_0; "\"Sql\\\\Common\\\\src\\\\IOCompletionP"...
0x1005b07d4  lea     rdx, aNullptrMThread; "nullptr == m_threadPool"
0x1005b07db  lea     ecx, [r14+1]; unsigned int
0x1005b07df  call    ?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x1005b07e4  mov     ebx, [rdi]
0x1005b07e6  mov     eax, 38h ; '8'
0x1005b07eb  mul     rbx
0x1005b07ee  mov     rdx, rax
0x1005b07f1  cmovo   rdx, r15
0x1005b07f5  cmp     rdx, r15
0x1005b07f8  jz      loc_1005B09D8
0x1005b07fe  mov     rcx, [rdi+10h]
0x1005b0802  lea     r8, aSqlCommonSrcIo; "Sql\\Common\\src\\IOCompletionPortThrea"...
0x1005b0809  mov     r9d, 13Ch
0x1005b080f  mov     byte ptr [rsp+0C8h+var_A8], 6
0x1005b0814  mov     rax, [rcx]
0x1005b0817  call    qword ptr [rax+50h]
0x1005b081a  test    rax, rax
0x1005b081d  jz      loc_1005B09D8
0x1005b0823  mov     [rsp+0C8h+arg_18], rsi
0x1005b082b  test    rbx, rbx
0x1005b082e  jz      short loc_1005B0865
0x1005b0830  lea     rcx, [rax+10h]
0x1005b0834  nop     dword ptr [rax+00h]
0x1005b0838  nop     dword ptr [rax+rax+00000000h]
0x1005b0840  mov     [rcx-10h], r14
0x1005b0844  mov     [rcx-8], r14b
0x1005b0848  mov     [rcx], r14
0x1005b084b  mov     [rcx+8], r14
0x1005b084f  mov     [rcx+10h], r14
0x1005b0853  mov     [rcx+18h], r14
0x1005b0857  mov     [rcx+20h], r14
0x1005b085b  lea     rcx, [rcx+38h]
0x1005b085f  sub     rbx, 1
0x1005b0863  jnz     short loc_1005B0840
0x1005b0865  mov     esi, r14d
0x1005b0868  mov     [rdi+18h], rax
0x1005b086c  cmp     [rdi], r14d
0x1005b086f  jbe     loc_1005B099D
0x1005b0875  mov     [rsp+0C8h+arg_10], rbp
0x1005b087d  mov     [rsp+0C8h+var_10], r12
0x1005b0885  lea     r12, qword_100714178
0x1005b088c  mov     [rsp+0C8h+var_18], r13
0x1005b0894  lea     r13, ?ListenOnIOCompletionPortEntryPoint@IOCompletionPortThreadPool@@CAPEAXPEAX@Z; IOCompletionPortThreadPool::ListenOnIOCompletionPortEntryPoint(void *)
0x1005b089b  nop     dword ptr [rax+rax+00h]
0x1005b08a0  mov     ecx, cs:?SOS_OS_NumberOfNodeInfos@@3KC; ulong volatile SOS_OS_NumberOfNodeInfos
0x1005b08a6  xor     edx, edx
0x1005b08a8  mov     eax, esi
0x1005b08aa  div     ecx
0x1005b08ac  movzx   eax, dx
0x1005b08af  mov     rbp, [r12+rax*8]
0x1005b08b3  test    rbp, rbp
0x1005b08b6  jz      short loc_1005B08C4
0x1005b08b8  test    byte ptr [rbp+620h], 10h
0x1005b08bf  jz      short loc_1005B08E7
0x1005b08c1  mov     rbp, r14
0x1005b08c4  mov     r9d, 146h; int
0x1005b08ca  mov     [rsp+0C8h+var_A8], r14; Format
0x1005b08cf  lea     r8, aSqlCommonSrcIo_0; "\"Sql\\\\Common\\\\src\\\\IOCompletionP"...
0x1005b08d6  mov     ecx, 1; unsigned int
0x1005b08db  lea     rdx, aNode; "node"
0x1005b08e2  call    ?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x1005b08e7  mov     rcx, [rdi+18h]
0x1005b08eb  lea     r8, qword_100716558; struct SOS_ResourceGroup *
0x1005b08f2  mov     eax, esi
0x1005b08f4  mov     r9, r15; unsigned __int64
0x1005b08f7  imul    rdx, rax, 38h ; '8'
0x1005b08fb  mov     rax, [rdi+8]
0x1005b08ff  mov     [rsp+0C8h+var_98], r14; struct SOS_Task *
0x1005b0904  mov     [rcx+rdx+28h], rax
0x1005b0909  lea     rcx, [rsp+0C8h+var_88]; this
0x1005b090e  mov     rax, [rdi+18h]
0x1005b0912  mov     [rax+rdx+18h], rbp
0x1005b0917  mov     rax, [rdi+18h]
0x1005b091b  mov     [rax+rdx+30h], rdi
0x1005b0920  mov     rbx, [rdi+18h]
0x1005b0924  add     rbx, rdx
0x1005b0927  mov     edx, 92h; unsigned int
0x1005b092c  mov     [rsp+0C8h+var_A0], rbx; void *
0x1005b0931  mov     [rsp+0C8h+var_A8], r13; void *(*)(void *)
0x1005b0936  call    ?Init@Param@SOS_Task@@QEAAXKPEAVSOS_ResourceGroup@@_KP6APEAXPEAX@Z2PEAV2@@Z; SOS_Task::Param::Init(ulong,SOS_ResourceGroup *,unsigned __int64,void * (*)(void *),void *,SOS_Task *)
0x1005b093b  lea     r9, [rbx+20h]
0x1005b093f  mov     [rsp+0C8h+var_A8], r14
0x1005b0944  xor     r8d, r8d
0x1005b0947  lea     rdx, [rsp+0C8h+var_88]
0x1005b094c  mov     rcx, rbp
0x1005b094f  call    ?EnqueueTaskDirectInternal@SOS_Node@@AEAA?AW4SOS_RESULT@@PEAVParam@SOS_Task@@PEAVSOSHost@@PEAPEAV4@PEAPEAX@Z; SOS_Node::EnqueueTaskDirectInternal(SOS_Task::Param *,SOSHost *,SOS_Task * *,void * *)
0x1005b0954  test    eax, eax
0x1005b0956  jz      short loc_1005B097B
0x1005b0958  mov     r9d, 151h; int
0x1005b095e  mov     [rsp+0C8h+var_A8], r14; Format
0x1005b0963  lea     r8, aSqlCommonSrcIo_0; "\"Sql\\\\Common\\\\src\\\\IOCompletionP"...
0x1005b096a  mov     ecx, 1; unsigned int
0x1005b096f  lea     rdx, aSosOkResult; "SOS_OK == result"
0x1005b0976  call    ?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x1005b097b  inc     esi
0x1005b097d  cmp     esi, [rdi]
0x1005b097f  jb      loc_1005B08A0
0x1005b0985  mov     r13, [rsp+0C8h+var_18]
0x1005b098d  mov     r12, [rsp+0C8h+var_10]
0x1005b0995  mov     rbp, [rsp+0C8h+arg_10]
0x1005b099d  mov     rsi, [rsp+0C8h+arg_18]
0x1005b09a5  xor     eax, eax
0x1005b09a7  mov     r14, [rsp+0C8h+var_20]
0x1005b09af  mov     rbx, [rsp+0C8h+arg_8]
0x1005b09b7  mov     r15, [rsp+0C8h+var_28]
0x1005b09bf  mov     rcx, [rsp+0C8h+var_38]
0x1005b09c7  xor     rcx, rsp; StackCookie
0x1005b09ca  call    __security_check_cookie
0x1005b09cf  add     rsp, 0C0h
0x1005b09d6  pop     rdi
0x1005b09d7  retn
0x1005b09d8  mov     [rdi+18h], r14
0x1005b09dc  mov     eax, 8007000Eh
0x1005b09e1  jmp     short loc_1005B09A7
0x1005b09e4  mov     eax, 80070057h
0x1005b09e9  jmp     short loc_1005B09BF
```
