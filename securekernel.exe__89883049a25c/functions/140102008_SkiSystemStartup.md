# SkiSystemStartup

- ea: `0x140102008`
- end: `0x1401022fb`
- name: `SkiSystemStartup`
- size: `755`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1400422d8`
- `0x14005a0f8`
- `0x1400890e8`
- `0x1400927e0`
- `0x140092cd0`
- `0x14009443c`
- `0x1400955f8`
- `0x14009aa08`
- `0x14009f434`
- `0x1400b86ec`
- `0x1400bb254`
- `0x1400bb398`
- `0x1400faec0`
- `0x140102008`
- `0x140102304`

## pseudocode

```c
NTSTATUS __stdcall SkiSystemStartup(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)
{
  _DWORD *v2; // r8
  _DWORD *v3; // r14
  int v4; // esi
  __int64 v6; // rdi
  NTSTATUS started; // edx
  unsigned __int64 v8; // rsi
  int inited; // eax
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rcx
  __int16 v13; // ax
  __int64 v14; // rcx
  __int64 *v15; // rcx
  int v16; // edx
  __int64 v17; // rax
  _BYTE *v18; // rax
  _BYTE *v19; // rcx
  __int64 v20; // r8
  _BYTE *v21; // rcx
  __int64 v22; // r8
  _BYTE *v23; // rcx
  __int64 v24; // r8

  v3 = v2;
  v4 = (int)RegistryPath;
  _security_init_cookie();
  if ( ((__int64)DriverObject[4].DriverStartIo & 0x2000) != 0 )
  {
    SkInfiniteLoop = 1;
    while ( SkInfiniteLoop == 1 )
      ;
  }
  v6 = 2336;
  if ( v4 != 2336 )
  {
    if ( !word_140109002 )
    {
      *(_DWORD *)SkInitFailure &= 0xFFFFFFF0;
      word_140109002 = 1;
      *(_DWORD *)SkInitFailure = *(_DWORD *)SkInitFailure & 0xFFFF000F | 0x10;
    }
    started = -1073741790;
    goto LABEL_24;
  }
  SkeLoaderBlock = (__int64)DriverObject;
  SkiInitializeSystemTsc(DriverObject);
  SkInitTraceLoggining(DriverObject, 0);
  v8 = __rdtsc();
  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(SkeLoaderBlock + 48) + 240LL) + 3520LL) = __rdtsc();
  SkiSetFeatureBits();
  SkeProcessorBlock[0] = (__int64)SkiInitialPrcbStorage;
  SkeProcessorBlockVp = (__int64)SkiInitialPrcbStorage;
  inited = ShvlInitSystem(0);
  started = inited;
  if ( inited < 0 )
  {
    if ( !word_140109002 )
    {
      *(_DWORD *)SkInitFailure &= 0xFFFFFFF0;
      word_140109002 = 3;
      *(_DWORD *)SkInitFailure = *(_DWORD *)SkInitFailure & 0xFFFF000F | 0x10;
    }
    goto LABEL_24;
  }
  SkhalSetFeatureBits(v10, (unsigned int)inited);
  v11 = SkmmInitSystem(0, 0);
  started = v11;
  if ( v11 >= 0 )
  {
    SkiArchPhase0Init(v12, (unsigned int)v11);
    started = SkeStartProcessor(0);
    if ( started < 0 )
    {
      if ( word_140109002 )
        goto LABEL_24;
      v13 = 7;
      goto LABEL_14;
    }
    v14 = *(_QWORD *)(SkeLoaderBlock + 72);
    SkImageBase = *(_QWORD *)(v14 + 48);
    SkImageSize = *(_DWORD *)(v14 + 64);
    SkpsSystemDirectoryTableBase = *(_QWORD *)(SkeLoaderBlock + 88);
    IumpCompactServiceTable();
    SkiCompactSecureServiceTable();
    v15 = SkiEnclaveServices;
    v16 = 4;
    do
    {
      v17 = *(unsigned int *)v15;
      v15 = (__int64 *)((char *)v15 + 4);
      *((_DWORD *)SkiSecureServiceTable + v17) |= 0x10u;
      --v16;
    }
    while ( v16 );
    started = SkInitSystem(0, 0);
    if ( started >= 0 )
    {
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(SkeLoaderBlock + 48) + 240LL) + 3528LL) = __rdtsc();
      SkWritePerfTraceEntry(0, 0, __rdtsc() - v8);
      started = ShvlInitializeVtl1();
      if ( started >= 0 )
        goto LABEL_36;
      goto LABEL_24;
    }
    if ( !word_140109002 )
    {
      v13 = 9;
      goto LABEL_14;
    }
  }
  else if ( !word_140109002 )
  {
    v13 = 5;
LABEL_14:
    *(_DWORD *)SkInitFailure &= 0xFFFFFFF0;
    word_140109002 = v13;
    *(_DWORD *)SkInitFailure = *(_DWORD *)SkInitFailure & 0xFFFF000F | 0x10;
  }
LABEL_24:
  if ( SkPhase1InitStatus >= 0 )
  {
    v18 = (_BYTE *)SkeLoaderBlock;
    if ( SkeLoaderBlock )
    {
      v19 = *(_BYTE **)(SkeLoaderBlock + 1448);
      if ( v19 )
      {
        v20 = *(unsigned int *)(SkeLoaderBlock + 1456);
        if ( *(_DWORD *)(SkeLoaderBlock + 1456) )
        {
          do
          {
            *v19++ = 0;
            --v20;
          }
          while ( v20 );
        }
      }
      v21 = (_BYTE *)*((_QWORD *)v18 + 176);
      if ( v21 )
      {
        v22 = *((unsigned int *)v18 + 354);
        if ( *((_DWORD *)v18 + 354) )
        {
          do
          {
            *v21++ = 0;
            --v22;
          }
          while ( v22 );
        }
      }
      v23 = (_BYTE *)*((_QWORD *)v18 + 239);
      if ( v23 )
      {
        v24 = *((unsigned int *)v18 + 480);
        if ( *((_DWORD *)v18 + 480) )
        {
          do
          {
            *v23++ = 0;
            --v24;
          }
          while ( v24 );
        }
      }
      do
      {
        *v18++ = 0;
        --v6;
      }
      while ( v6 );
    }
  }
LABEL_36:
  *v3 = *(_DWORD *)SkInitFailure;
  return started;
}

```

## disassembly

```asm
0x140102008  push    rbx
0x14010200a  push    rbp
0x14010200b  push    rsi
0x14010200c  push    rdi
0x14010200d  push    r14
0x14010200f  sub     rsp, 20h
0x140102013  mov     r14, r8
0x140102016  mov     esi, edx
0x140102018  mov     rbx, rcx
0x14010201b  call    __security_init_cookie
0x140102020  test    dword ptr [rbx+5A0h], 2000h
0x14010202a  mov     ebp, 1
0x14010202f  jz      short loc_140102043
0x140102031  mov     cs:SkInfiniteLoop, bpl
0x140102038  mov     al, cs:SkInfiniteLoop
0x14010203e  cmp     al, bpl
0x140102041  jz      short loc_140102038
0x140102043  mov     edi, 920h
0x140102048  cmp     esi, edi
0x14010204a  jz      short loc_140102083
0x14010204c  xor     ebx, ebx
0x14010204e  cmp     cs:word_140109002, bx
0x140102055  jnz     short loc_140102079
0x140102057  and     dword ptr cs:SkInitFailure, 0FFFFFFF0h
0x14010205e  mov     cs:word_140109002, bp
0x140102065  mov     eax, dword ptr cs:SkInitFailure
0x14010206b  and     eax, 0FFFF001Fh
0x140102070  or      eax, 10h
0x140102073  mov     dword ptr cs:SkInitFailure, eax
0x140102079  mov     edx, 0C0000022h
0x14010207e  jmp     loc_140102260
0x140102083  mov     rcx, rbx
0x140102086  mov     cs:SkeLoaderBlock, rbx
0x14010208d  call    SkiInitializeSystemTsc
0x140102092  mov     rcx, rbx
0x140102095  xor     edx, edx
0x140102097  call    SkInitTraceLoggining
0x14010209c  rdtsc
0x14010209e  shl     rdx, 20h
0x1401020a2  or      rax, rdx
0x1401020a5  mov     rsi, rax
0x1401020a8  rdtsc
0x1401020aa  shl     rdx, 20h
0x1401020ae  or      rdx, rax
0x1401020b1  mov     rax, cs:SkeLoaderBlock
0x1401020b8  mov     rcx, [rax+30h]
0x1401020bc  mov     rax, [rcx+0F0h]
0x1401020c3  mov     [rax+0DC0h], rdx
0x1401020ca  call    SkiSetFeatureBits
0x1401020cf  lea     rax, SkiInitialPrcbStorage
0x1401020d6  xor     ecx, ecx
0x1401020d8  mov     cs:SkeProcessorBlock, rax
0x1401020df  mov     cs:SkeProcessorBlockVp, rax
0x1401020e6  call    ShvlInitSystem
0x1401020eb  xor     ebx, ebx
0x1401020ed  mov     edx, eax
0x1401020ef  test    eax, eax
0x1401020f1  jns     short loc_14010212B
0x1401020f3  cmp     cs:word_140109002, bx
0x1401020fa  jnz     loc_140102260
0x140102100  and     dword ptr cs:SkInitFailure, 0FFFFFFF0h
0x140102107  lea     eax, [rbx+3]
0x14010210a  mov     cs:word_140109002, ax
0x140102111  mov     ecx, dword ptr cs:SkInitFailure
0x140102117  and     ecx, 0FFFF001Fh
0x14010211d  or      ecx, 10h
0x140102120  mov     dword ptr cs:SkInitFailure, ecx
0x140102126  jmp     loc_140102260
0x14010212b  call    SkhalSetFeatureBits
0x140102130  xor     edx, edx
0x140102132  xor     ecx, ecx
0x140102134  call    SkmmInitSystem
0x140102139  mov     edx, eax
0x14010213b  test    eax, eax
0x14010213d  jns     short loc_140102178
0x14010213f  cmp     cs:word_140109002, bx
0x140102146  jnz     loc_140102260
0x14010214c  mov     eax, 5
0x140102151  and     dword ptr cs:SkInitFailure, 0FFFFFFF0h
0x140102158  mov     cs:word_140109002, ax
0x14010215f  mov     eax, dword ptr cs:SkInitFailure
0x140102165  and     eax, 0FFFF001Fh
0x14010216a  or      eax, 10h
0x14010216d  mov     dword ptr cs:SkInitFailure, eax
0x140102173  jmp     loc_140102260
0x140102178  call    SkiArchPhase0Init
0x14010217d  xor     ecx, ecx
0x14010217f  call    SkeStartProcessor
0x140102184  mov     edx, eax
0x140102186  test    eax, eax
0x140102188  jns     short loc_14010219E
0x14010218a  cmp     cs:word_140109002, bx
0x140102191  jnz     loc_140102260
0x140102197  mov     eax, 7
0x14010219c  jmp     short loc_140102151
0x14010219e  mov     rdx, cs:SkeLoaderBlock
0x1401021a5  mov     rcx, [rdx+48h]
0x1401021a9  mov     rax, [rcx+30h]
0x1401021ad  mov     cs:SkImageBase, rax
0x1401021b4  mov     eax, [rcx+40h]
0x1401021b7  mov     cs:SkImageSize, eax
0x1401021bd  mov     rax, [rdx+58h]
0x1401021c1  mov     cs:SkpsSystemDirectoryTableBase, rax
0x1401021c8  call    IumpCompactServiceTable
0x1401021cd  call    SkiCompactSecureServiceTable
0x1401021d2  lea     rcx, SkiEnclaveServices
0x1401021d9  mov     edx, 4
0x1401021de  mov     eax, [rcx]
0x1401021e0  lea     r8, SkiSecureServiceTable
0x1401021e7  lea     rcx, [rcx+4]
0x1401021eb  or      dword ptr [r8+rax*4], 10h
0x1401021f0  add     edx, 0FFFFFFFFh
0x1401021f3  jnz     short loc_1401021DE
0x1401021f5  xor     edx, edx
0x1401021f7  xor     ecx, ecx
0x1401021f9  call    SkInitSystem
0x1401021fe  mov     edx, eax
0x140102200  test    eax, eax
0x140102202  jns     short loc_140102217
0x140102204  cmp     cs:word_140109002, bx
0x14010220b  jnz     short loc_140102260
0x14010220d  mov     eax, 9
0x140102212  jmp     loc_140102151
0x140102217  rdtsc
0x140102219  mov     rcx, cs:SkeLoaderBlock
0x140102220  shl     rdx, 20h
0x140102224  or      rax, rdx
0x140102227  mov     rdx, [rcx+30h]
0x14010222b  mov     rcx, [rdx+0F0h]
0x140102232  mov     [rcx+0DC8h], rax
0x140102239  rdtsc
0x14010223b  shl     rdx, 20h
0x14010223f  xor     ecx, ecx
0x140102241  or      rax, rdx
0x140102244  xor     edx, edx
0x140102246  sub     rax, rsi
0x140102249  mov     r8, rax
0x14010224c  call    SkWritePerfTraceEntry
0x140102251  call    ShvlInitializeVtl1
0x140102256  mov     edx, eax
0x140102258  test    eax, eax
0x14010225a  jns     loc_1401022E4
0x140102260  cmp     cs:SkPhase1InitStatus, ebx
0x140102266  jl      short loc_1401022E4
0x140102268  mov     rax, cs:SkeLoaderBlock
0x14010226f  test    rax, rax
0x140102272  jz      short loc_1401022E4
0x140102274  mov     rcx, [rax+5A8h]
0x14010227b  test    rcx, rcx
0x14010227e  jz      short loc_140102296
0x140102280  mov     r8d, [rax+5B0h]
0x140102287  test    r8, r8
0x14010228a  jz      short loc_140102296
0x14010228c  mov     [rcx], bl
0x14010228e  add     rcx, rbp
0x140102291  sub     r8, rbp
0x140102294  jnz     short loc_14010228C
0x140102296  mov     rcx, [rax+580h]
0x14010229d  test    rcx, rcx
0x1401022a0  jz      short loc_1401022B8
0x1401022a2  mov     r8d, [rax+588h]
0x1401022a9  test    r8, r8
0x1401022ac  jz      short loc_1401022B8
0x1401022ae  mov     [rcx], bl
0x1401022b0  add     rcx, rbp
0x1401022b3  sub     r8, rbp
0x1401022b6  jnz     short loc_1401022AE
0x1401022b8  mov     rcx, [rax+778h]
0x1401022bf  test    rcx, rcx
0x1401022c2  jz      short loc_1401022DA
0x1401022c4  mov     r8d, [rax+780h]
0x1401022cb  test    r8, r8
0x1401022ce  jz      short loc_1401022DA
0x1401022d0  mov     [rcx], bl
0x1401022d2  add     rcx, rbp
0x1401022d5  sub     r8, rbp
0x1401022d8  jnz     short loc_1401022D0
0x1401022da  mov     [rax], bl
0x1401022dc  add     rax, rbp
0x1401022df  sub     rdi, rbp
0x1401022e2  jnz     short loc_1401022DA
0x1401022e4  mov     eax, dword ptr cs:SkInitFailure
0x1401022ea  mov     [r14], eax
0x1401022ed  mov     eax, edx
0x1401022ef  add     rsp, 20h
0x1401022f3  pop     r14
0x1401022f5  pop     rdi
0x1401022f6  pop     rsi
0x1401022f7  pop     rbp
0x1401022f8  pop     rbx
0x1401022f9  retn
```
