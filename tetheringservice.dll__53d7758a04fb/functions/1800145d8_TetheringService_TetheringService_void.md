# TetheringService::TetheringService(void)

- ea: `0x1800145d8`
- end: `0x180014a06`
- name: `??0TetheringService@@QEAA@XZ`
- size: `1070`
- prototype: `TetheringService *__fastcall(TetheringService *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b888`

## callees

- `0x180003088`
- `0x18000bf4c`
- `0x18000ee14`
- `0x1800145d8`
- `0x180019334`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800146d6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800147e6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001494e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001495b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180014968`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180014975`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180014982`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001498f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001499c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800146d6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800147e6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001494e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001495b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180014968`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180014975`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180014982`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001498f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001499c`

## pseudocode

```c
TetheringService *__fastcall TetheringService::TetheringService(TetheringService *this)
{
  _OWORD *v2; // rcx
  _OWORD *v3; // rax
  __int64 v4; // rdx
  int v5; // eax
  _BYTE v7[552]; // [rsp+20h] [rbp-228h] BYREF

  *(_QWORD *)this = &TetheringService::`vftable';
  *((_BYTE *)this + 220) = 0;
  *((_DWORD *)this + 56) = 3;
  *((_QWORD *)this + 39) = 0;
  *((_QWORD *)this + 40) = 0;
  *((_QWORD *)this + 41) = 0;
  *((_BYTE *)this + 336) = 0;
  *(_QWORD *)((char *)this + 340) = 0;
  *((_DWORD *)this + 88) = 36;
  *((_QWORD *)this + 50) = 0;
  *((_QWORD *)this + 51) = 0;
  *((_DWORD *)this + 112) = 0;
  *(GUID *)((char *)this + 452) = GUID_NULL;
  *(_QWORD *)((char *)this + 468) = 0;
  *((_DWORD *)this + 119) = 0;
  *(GUID *)((char *)this + 524) = GUID_NULL;
  *(_QWORD *)((char *)this + 540) = 0;
  *((_QWORD *)this + 69) = 0;
  *((_DWORD *)this + 140) = 0;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids);
  }
  *((_OWORD *)this + 26) = 0;
  *((_OWORD *)this + 27) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)this + 9);
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids);
  }
  *((_QWORD *)this + 71) = 0;
  *((_QWORD *)this + 72) = 0;
  *((_QWORD *)this + 73) = 0;
  *((_QWORD *)this + 74) = 0;
  *(_OWORD *)((char *)this + 600) = 0;
  *((_DWORD *)this + 154) = 0;
  *((_BYTE *)this + 662) = 0;
  memset_0(v7, 0, 0x208u);
  v2 = (_OWORD *)((char *)this + 664);
  v3 = v7;
  v4 = 4;
  do
  {
    *v2 = *v3;
    v2[1] = v3[1];
    v2[2] = v3[2];
    v2[3] = v3[3];
    v2[4] = v3[4];
    v2[5] = v3[5];
    v2[6] = v3[6];
    v2[7] = v3[7];
    v2 += 8;
    v3 += 8;
    --v4;
  }
  while ( v4 );
  *(_QWORD *)v2 = *(_QWORD *)v3;
  *((_QWORD *)this + 148) = 0;
  *((_DWORD *)this + 298) = 0;
  *((_QWORD *)this + 152) = 0;
  *((_QWORD *)this + 153) = 0;
  *((_QWORD *)this + 154) = 0;
  *((_WORD *)this + 640) = 0;
  *((_QWORD *)this + 150) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)this + 31);
  *((_QWORD *)this + 175) = 0;
  *((_QWORD *)this + 191) = 0;
  *((_BYTE *)this + 1536) = 0;
  *((_QWORD *)this + 193) = 0;
  *((_QWORD *)this + 194) = 0;
  *((_QWORD *)this + 195) = 0;
  *((_BYTE *)this + 1568) = 1;
  *((_QWORD *)this + 197) = 0;
  *((_QWORD *)this + 198) = 0;
  *((_DWORD *)this + 398) = -1;
  *((_QWORD *)this + 200) = 0;
  *((_QWORD *)this + 201) = 0;
  *((_DWORD *)this + 404) = -1;
  *((_QWORD *)this + 203) = 0;
  *((_QWORD *)this + 204) = 0;
  *((_DWORD *)this + 410) = -1;
  *((_DWORD *)this + 412) = 0;
  *(_QWORD *)((char *)this + 1652) = 7;
  *((_DWORD *)this + 415) = 0;
  *((_WORD *)this + 832) = 0;
  *((_DWORD *)this + 417) = 0;
  *((_QWORD *)this + 209) = 0;
  *((_QWORD *)this + 210) = 0;
  *((_QWORD *)this + 211) = 0;
  *((_QWORD *)this + 212) = 0;
  *((_QWORD *)this + 213) = 0;
  *((_QWORD *)this + 214) = TetheringService::InterfaceOperStatusChangeCallback;
  *((_QWORD *)this + 215) = this;
  *((_QWORD *)this + 216) = 0;
  *((_QWORD *)this + 217) = 0;
  *((_DWORD *)this + 437) = 1;
  *(_OWORD *)((char *)this + 1752) = 0;
  *(_OWORD *)((char *)this + 1768) = 0;
  *((_QWORD *)this + 223) = 0;
  v5 = ATL::CComCriticalSection::Init((TetheringService *)((char *)this + 1752));
  if ( v5 < 0 )
    ATL::AtlThrowImpl(v5);
  *((_BYTE *)this + 1792) = 0;
  *((_QWORD *)this + 225) = -1;
  *((_QWORD *)this + 235) = 0;
  *((_DWORD *)this + 472) = 0;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
  *(GUID *)((char *)this + 1288) = GUID_NULL;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 272));
  InitializeCriticalSection((LPCRITICAL_SECTION)this + 34);
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 1304));
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 1408));
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 1448));
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 1488));
  *((_QWORD *)this + 169) = (char *)this + 1344;
  *((_QWORD *)this + 168) = (char *)this + 1344;
  *(GUID *)((char *)this + 1288) = GUID_NULL;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
  return this;
}

```

## disassembly

```asm
0x1800145d8  mov     [rsp+arg_10], rbx
0x1800145dd  mov     [rsp+arg_0], rcx
0x1800145e2  push    rsi
0x1800145e3  push    rdi
0x1800145e4  push    r14
0x1800145e6  sub     rsp, 230h
0x1800145ed  mov     rbx, rcx
0x1800145f0  lea     rax, ??_7TetheringService@@6B@; const TetheringService::`vftable'
0x1800145f7  mov     [rcx], rax
0x1800145fa  xor     esi, esi
0x1800145fc  mov     [rcx+0DCh], sil
0x180014603  mov     dword ptr [rcx+0E0h], 3
0x18001460d  mov     [rcx+138h], rsi
0x180014614  mov     [rcx+140h], rsi
0x18001461b  mov     [rcx+148h], rsi
0x180014622  mov     [rcx+150h], sil
0x180014629  mov     [rcx+154h], rsi
0x180014630  mov     dword ptr [rcx+160h], 24h ; '$'
0x18001463a  mov     [rcx+190h], rsi
0x180014641  mov     [rcx+198h], rsi
0x180014648  mov     [rcx+1C0h], esi
0x18001464e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180014655  movdqu  xmmword ptr [rcx+1C4h], xmm0
0x18001465d  mov     [rcx+1D4h], rsi
0x180014664  mov     [rcx+1DCh], esi
0x18001466a  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180014671  movdqu  xmmword ptr [rcx+20Ch], xmm0
0x180014679  mov     [rcx+21Ch], rsi
0x180014680  mov     [rcx+228h], rsi
0x180014687  mov     [rcx+230h], esi
0x18001468d  lea     r14, WPP_GLOBAL_Control
0x180014694  mov     rcx, cs:WPP_GLOBAL_Control
0x18001469b  cmp     rcx, r14
0x18001469e  jz      short loc_1800146B9
0x1800146a0  test    byte ptr [rcx+1Ch], 8
0x1800146a4  jz      short loc_1800146B9
0x1800146a6  lea     edx, [rsi+0Ah]
0x1800146a9  lea     r8, WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids
0x1800146b0  mov     rcx, [rcx+10h]
0x1800146b4  call    WPP_SF_
0x1800146b9  xorps   xmm0, xmm0
0x1800146bc  movdqu  xmmword ptr [rbx+1A0h], xmm0
0x1800146c4  xorps   xmm1, xmm1
0x1800146c7  movdqu  xmmword ptr [rbx+1B0h], xmm1
0x1800146cf  lea     rcx, [rbx+168h]; lpCriticalSection
0x1800146d6  call    cs:__imp_InitializeCriticalSection
0x1800146dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800146e3  cmp     rcx, r14
0x1800146e6  jz      short loc_180014704
0x1800146e8  test    byte ptr [rcx+1Ch], 8
0x1800146ec  jz      short loc_180014704
0x1800146ee  mov     edx, 0Bh
0x1800146f3  lea     r8, WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids
0x1800146fa  mov     rcx, [rcx+10h]
0x1800146fe  call    WPP_SF_
0x180014703  nop
0x180014704  mov     [rbx+238h], rsi
0x18001470b  mov     [rbx+240h], rsi
0x180014712  mov     [rbx+248h], rsi
0x180014719  mov     [rbx+250h], rsi
0x180014720  xorps   xmm0, xmm0
0x180014723  movdqu  xmmword ptr [rbx+258h], xmm0
0x18001472b  mov     [rbx+268h], esi
0x180014731  mov     [rbx+296h], sil
0x180014738  xor     edx, edx; Val
0x18001473a  mov     r8d, 208h; Size
0x180014740  lea     rcx, [rsp+248h+var_228]; void *
0x180014745  call    memset_0
0x18001474a  lea     rcx, [rbx+298h]
0x180014751  lea     rax, [rsp+248h+var_228]
0x180014756  mov     edx, 4
0x18001475b  lea     r8d, [rdx+7Ch]
0x18001475f  movups  xmm0, xmmword ptr [rax]
0x180014762  movups  xmmword ptr [rcx], xmm0
0x180014765  movups  xmm1, xmmword ptr [rax+10h]
0x180014769  movups  xmmword ptr [rcx+10h], xmm1
0x18001476d  movups  xmm0, xmmword ptr [rax+20h]
0x180014771  movups  xmmword ptr [rcx+20h], xmm0
0x180014775  movups  xmm1, xmmword ptr [rax+30h]
0x180014779  movups  xmmword ptr [rcx+30h], xmm1
0x18001477d  movups  xmm0, xmmword ptr [rax+40h]
0x180014781  movups  xmmword ptr [rcx+40h], xmm0
0x180014785  movups  xmm1, xmmword ptr [rax+50h]
0x180014789  movups  xmmword ptr [rcx+50h], xmm1
0x18001478d  movups  xmm0, xmmword ptr [rax+60h]
0x180014791  movups  xmmword ptr [rcx+60h], xmm0
0x180014795  movups  xmm1, xmmword ptr [rax+70h]
0x180014799  movups  xmmword ptr [rcx+70h], xmm1
0x18001479d  add     rcx, r8
0x1800147a0  add     rax, r8
0x1800147a3  sub     rdx, 1
0x1800147a7  jnz     short loc_18001475F
0x1800147a9  mov     rax, [rax]
0x1800147ac  mov     [rcx], rax
0x1800147af  mov     [rbx+4A0h], rsi
0x1800147b6  mov     [rbx+4A8h], esi
0x1800147bc  mov     [rbx+4C0h], rsi
0x1800147c3  mov     [rbx+4C8h], rsi
0x1800147ca  mov     [rbx+4D0h], rsi
0x1800147d1  mov     [rbx+500h], si
0x1800147d8  mov     [rbx+4B0h], rsi
0x1800147df  lea     rcx, [rbx+4D8h]; lpCriticalSection
0x1800147e6  call    cs:__imp_InitializeCriticalSection
0x1800147ec  nop
0x1800147ed  mov     [rbx+578h], rsi
0x1800147f4  mov     [rbx+5F8h], rsi
0x1800147fb  mov     [rbx+600h], sil
0x180014802  mov     [rbx+608h], rsi
0x180014809  mov     [rbx+610h], rsi
0x180014810  mov     [rbx+618h], rsi
0x180014817  mov     byte ptr [rbx+620h], 1
0x18001481e  mov     [rbx+628h], rsi
0x180014825  mov     [rbx+630h], rsi
0x18001482c  or      eax, 0FFFFFFFFh
0x18001482f  mov     [rbx+638h], eax
0x180014835  mov     [rbx+640h], rsi
0x18001483c  mov     [rbx+648h], rsi
0x180014843  mov     [rbx+650h], eax
0x180014849  mov     [rbx+658h], rsi
0x180014850  mov     [rbx+660h], rsi
0x180014857  mov     [rbx+668h], eax
0x18001485d  mov     [rbx+670h], esi
0x180014863  mov     qword ptr [rbx+674h], 7
0x18001486e  mov     [rbx+67Ch], esi
0x180014874  mov     [rbx+680h], si
0x18001487b  mov     [rbx+684h], esi
0x180014881  mov     [rbx+688h], rsi
0x180014888  mov     [rbx+690h], rsi
0x18001488f  mov     [rbx+698h], rsi
0x180014896  mov     [rbx+6A0h], rsi
0x18001489d  mov     [rbx+6A8h], rsi
0x1800148a4  lea     rax, ?InterfaceOperStatusChangeCallback@TetheringService@@CAXAEBT_NET_LUID_LH@@W4IF_OPER_STATUS@@PEAX@Z; TetheringService::InterfaceOperStatusChangeCallback(_NET_LUID_LH const &,IF_OPER_STATUS,void *)
0x1800148ab  mov     [rbx+6B0h], rax
0x1800148b2  mov     [rbx+6B8h], rbx
0x1800148b9  mov     [rbx+6C0h], rsi
0x1800148c0  mov     [rbx+6C8h], rsi
0x1800148c7  mov     dword ptr [rbx+6D4h], 1
0x1800148d1  lea     rdi, [rbx+6D8h]
0x1800148d8  xorps   xmm0, xmm0
0x1800148db  xor     eax, eax
0x1800148dd  movups  xmmword ptr [rdi], xmm0
0x1800148e0  movups  xmmword ptr [rdi+10h], xmm0
0x1800148e4  mov     [rdi+20h], rax
0x1800148e8  mov     rcx, rdi; this
0x1800148eb  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800148f0  test    eax, eax
0x1800148f2  js      loc_1800149FE
0x1800148f8  mov     [rdi+28h], sil
0x1800148fc  mov     qword ptr [rdi+30h], 0FFFFFFFFFFFFFFFFh
0x180014904  mov     [rbx+758h], rsi
0x18001490b  mov     [rbx+760h], esi
0x180014911  mov     rcx, cs:WPP_GLOBAL_Control
0x180014918  cmp     rcx, r14
0x18001491b  jz      short loc_180014938
0x18001491d  test    byte ptr [rcx+1Ch], 8
0x180014921  jz      short loc_180014938
0x180014923  mov     edx, 0Ah
0x180014928  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001492f  mov     rcx, [rcx+10h]
0x180014933  call    WPP_SF_
0x180014938  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001493f  movdqu  xmmword ptr [rbx+508h], xmm0
0x180014947  lea     rcx, [rbx+0E8h]; lpCriticalSection
0x18001494e  call    cs:__imp_InitializeCriticalSection
0x180014954  lea     rcx, [rbx+110h]; lpCriticalSection
0x18001495b  call    cs:__imp_InitializeCriticalSection
0x180014961  lea     rcx, [rbx+550h]; lpCriticalSection
0x180014968  call    cs:__imp_InitializeCriticalSection
0x18001496e  lea     rcx, [rbx+518h]; lpCriticalSection
0x180014975  call    cs:__imp_InitializeCriticalSection
0x18001497b  lea     rcx, [rbx+580h]; lpCriticalSection
0x180014982  call    cs:__imp_InitializeCriticalSection
0x180014988  lea     rcx, [rbx+5A8h]; lpCriticalSection
0x18001498f  call    cs:__imp_InitializeCriticalSection
0x180014995  lea     rcx, [rbx+5D0h]; lpCriticalSection
0x18001499c  call    cs:__imp_InitializeCriticalSection
0x1800149a2  lea     rax, [rbx+540h]
0x1800149a9  mov     [rax+8], rax
0x1800149ad  mov     [rax], rax
0x1800149b0  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800149b7  movdqu  xmmword ptr [rbx+508h], xmm0
0x1800149bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800149c6  cmp     rcx, r14
0x1800149c9  jz      short loc_1800149E7
0x1800149cb  test    byte ptr [rcx+1Ch], 8
0x1800149cf  jz      short loc_1800149E7
0x1800149d1  mov     edx, 0Bh
0x1800149d6  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x1800149dd  mov     rcx, [rcx+10h]
0x1800149e1  call    WPP_SF_
0x1800149e6  nop
0x1800149e7  mov     rax, rbx
0x1800149ea  mov     rbx, [rsp+248h+arg_10]
0x1800149f2  add     rsp, 230h
0x1800149f9  pop     r14
0x1800149fb  pop     rdi
0x1800149fc  pop     rsi
0x1800149fd  retn
0x1800149fe  mov     ecx, eax; int
0x180014a00  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
