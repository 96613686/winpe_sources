# CWcnPeer::SetDiscoveryVendorExtensions(std::vector<CSbSafeBuffer *,std::allocator<CSbSafeBuffer *>> const *)

- ea: `0x18001dbbc`
- end: `0x18001de07`
- name: `?SetDiscoveryVendorExtensions@CWcnPeer@@QEAAJPEBV?$vector@PEAVCSbSafeBuffer@@V?$allocator@PEAVCSbSafeBuffer@@@std@@@std@@@Z`
- size: `587`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting`

## callers

- `0x180014fa4`

## callees

- `0x180001404`
- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x18000a558`
- `0x18000a5ac`
- `0x18000a74c`
- `0x18001dbbc`
- `0x18001e078`
- `0x180053004`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001dc4f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001dc7a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001dc8e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001dc4f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001dc7a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001dc8e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001dc1e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001dc1e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ddb5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ddb5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWcnPeer::SetDiscoveryVendorExtensions(__int64 a1, _QWORD *a2)
{
  _QWORD *v2; // r15
  int v4; // edi
  const char *Indent; // rax
  __int64 v6; // r10
  CSbSafeBuffer ***v7; // rsi
  CSbSafeBuffer **v8; // r12
  CSbSafeBuffer **v9; // rsi
  CSbSafeBuffer *v10; // r15
  __int64 v11; // rsi
  _QWORD *v12; // rax
  _QWORD *v13; // rsi
  __int64 v14; // rdx
  unsigned __int64 i; // rsi
  CSbSafeBuffer *v16; // rax
  CSbSafeBuffer *v17; // rdx
  int v18; // eax
  unsigned int v19; // eax
  __int64 v20; // r10
  __int64 v22; // rax
  std::bad_alloc *v23; // [rsp+30h] [rbp-48h] BYREF
  CSbSafeBuffer *v24; // [rsp+80h] [rbp+8h] BYREF
  _QWORD *v25; // [rsp+88h] [rbp+10h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+90h] [rbp+18h]
  _QWORD *v27; // [rsp+98h] [rbp+20h]

  v25 = a2;
  v2 = a2;
  v4 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v6 + 16), 20, WPP_805ccd1b393d3e4b99a4efc8134fe3a0_Traceguids, Indent);
  }
  lpCriticalSection = (LPCRITICAL_SECTION)(a1 + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  v7 = *(CSbSafeBuffer ****)(a1 + 256);
  if ( v7 )
  {
    v8 = v7[1];
    v9 = *v7;
    if ( v9 != v8 )
    {
      do
      {
        v10 = *v9;
        if ( *v9 )
        {
          CSbSafeBuffer::~CSbSafeBuffer(*v9);
          operator delete(v10);
        }
        ++v9;
      }
      while ( v9 != v8 );
      v2 = v25;
    }
    v11 = *(_QWORD *)(a1 + 256);
    if ( v11 )
    {
      if ( *(_QWORD *)v11 )
      {
        operator delete(*(void **)v11);
        *(_QWORD *)v11 = 0;
        *(_QWORD *)(v11 + 8) = 0;
        *(_QWORD *)(v11 + 16) = 0;
      }
      operator delete((void *)v11);
    }
    *(_QWORD *)(a1 + 256) = 0;
  }
  try
  {
    v12 = operator new(0x18u);
    v13 = v12;
    v27 = v12;
    if ( v12 )
    {
      v24 = 0;
      v14 = (__int64)(v2[1] - *v2) >> 3;
      *v12 = 0;
      v12[1] = 0;
      v12[2] = 0;
      std::vector<CSbSafeBuffer *>::_Construct_n(v12, v14, &v24);
    }
    else
    {
      v13 = 0;
    }
    *(_QWORD *)(a1 + 256) = v13;
    for ( i = 0; i < (__int64)(v2[1] - *v2) >> 3; ++i )
    {
      v16 = (CSbSafeBuffer *)operator new(0x20u);
      v24 = v16;
      if ( v16 )
        v17 = CSbSafeBuffer::CSbSafeBuffer(v16);
      else
        v17 = 0;
      *(_QWORD *)(**(_QWORD **)(a1 + 256) + 8 * i) = v17;
      v18 = CSbSafeBuffer::CopyFromBuffer(
              *(CSbSafeBuffer **)(**(_QWORD **)(a1 + 256) + 8 * i),
              *(const struct CSbSafeBuffer **)(*v2 + 8 * i));
      v4 = v18;
      if ( v18 < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            21,
            WPP_805ccd1b393d3e4b99a4efc8134fe3a0_Traceguids,
            (unsigned int)v18);
        goto LABEL_40;
      }
    }
  }
  catch ( std::bad_alloc *v23 )
  {
    LODWORD(v24) = -2147024882;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v22 = (*(__int64 (__fastcall **)(std::bad_alloc *))(*(_QWORD *)v23 + 8LL))(v23);
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_805ccd1b393d3e4b99a4efc8134fe3a0_Traceguids, v22);
    }
    v4 = (int)v24;
  }
LABEL_40:
  LeaveCriticalSection(lpCriticalSection);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (v4 < 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u) )
  {
    v19 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v20 + 16), 23, (unsigned int)WPP_805ccd1b393d3e4b99a4efc8134fe3a0_Traceguids, v19, v4);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001dbbc  mov     [rsp+arg_8], rdx
0x18001dbc1  push    rsi
0x18001dbc2  push    rdi
0x18001dbc3  push    r12
0x18001dbc5  push    r13
0x18001dbc7  push    r14
0x18001dbc9  push    r15
0x18001dbcb  sub     rsp, 48h
0x18001dbcf  mov     r15, rdx
0x18001dbd2  mov     r14, rcx
0x18001dbd5  xor     edi, edi
0x18001dbd7  lea     r13, WPP_GLOBAL_Control
0x18001dbde  mov     r10, cs:WPP_GLOBAL_Control
0x18001dbe5  cmp     r10, r13
0x18001dbe8  jz      short loc_18001DC0F
0x18001dbea  cmp     byte ptr [r10+19h], 6
0x18001dbef  jb      short loc_18001DC0F
0x18001dbf1  lea     ecx, [rdi+1]; int
0x18001dbf4  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001dbf9  lea     edx, [rdi+14h]
0x18001dbfc  mov     r9, rax
0x18001dbff  lea     r8, WPP_805ccd1b393d3e4b99a4efc8134fe3a0_Traceguids
0x18001dc06  mov     rcx, [r10+10h]
0x18001dc0a  call    WPP_SF_s
0x18001dc0f  lea     rax, [r14+10h]
0x18001dc13  mov     [rsp+78h+lpCriticalSection], rax
0x18001dc1b  mov     rcx, rax; lpCriticalSection
0x18001dc1e  call    cs:__imp_EnterCriticalSection
0x18001dc24  mov     rsi, [r14+100h]
0x18001dc2b  test    rsi, rsi
0x18001dc2e  jz      short loc_18001DC9B
0x18001dc30  mov     r12, [rsi+8]
0x18001dc34  mov     rsi, [rsi]
0x18001dc37  cmp     rsi, r12
0x18001dc3a  jz      short loc_18001DC66
0x18001dc3c  mov     r15, [rsi]
0x18001dc3f  test    r15, r15
0x18001dc42  jz      short loc_18001DC55
0x18001dc44  mov     rcx, r15; this
0x18001dc47  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x18001dc4c  mov     rcx, r15
0x18001dc4f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001dc55  add     rsi, 8
0x18001dc59  cmp     rsi, r12
0x18001dc5c  jnz     short loc_18001DC3C
0x18001dc5e  mov     r15, [rsp+78h+arg_8]
0x18001dc66  mov     rsi, [r14+100h]
0x18001dc6d  test    rsi, rsi
0x18001dc70  jz      short loc_18001DC94
0x18001dc72  cmp     [rsi], rdi
0x18001dc75  jz      short loc_18001DC8B
0x18001dc77  mov     rcx, [rsi]
0x18001dc7a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001dc80  mov     [rsi], rdi
0x18001dc83  mov     [rsi+8], rdi
0x18001dc87  mov     [rsi+10h], rdi
0x18001dc8b  mov     rcx, rsi
0x18001dc8e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001dc94  mov     [r14+100h], rdi
0x18001dc9b  mov     ecx, 18h; Size
0x18001dca0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001dca5  mov     rsi, rax
0x18001dca8  mov     [rsp+78h+arg_18], rax
0x18001dcb0  test    rax, rax
0x18001dcb3  jz      short loc_18001DCF5
0x18001dcb5  mov     [rsp+78h+arg_0], 0
0x18001dcc1  mov     rdx, [r15+8]
0x18001dcc5  sub     rdx, [r15]
0x18001dcc8  sar     rdx, 3
0x18001dccc  mov     qword ptr [rax], 0
0x18001dcd3  mov     qword ptr [rax+8], 0
0x18001dcdb  mov     qword ptr [rax+10h], 0
0x18001dce3  lea     r8, [rsp+78h+arg_0]
0x18001dceb  mov     rcx, rax
0x18001dcee  call    ?_Construct_n@?$vector@PEAVCSbSafeBuffer@@V?$allocator@PEAVCSbSafeBuffer@@@std@@@std@@QEAAX_KPEBQEAVCSbSafeBuffer@@@Z; std::vector<CSbSafeBuffer *>::_Construct_n(unsigned __int64,CSbSafeBuffer * const *)
0x18001dcf3  jmp     short loc_18001DCF7
0x18001dcf5  xor     esi, esi
0x18001dcf7  mov     [r14+100h], rsi
0x18001dcfe  xor     esi, esi
0x18001dd00  mov     rax, [r15+8]
0x18001dd04  sub     rax, [r15]
0x18001dd07  sar     rax, 3
0x18001dd0b  cmp     rsi, rax
0x18001dd0e  jnb     loc_18001DD9D
0x18001dd14  mov     ecx, 20h ; ' '; Size
0x18001dd19  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001dd1e  mov     [rsp+78h+arg_0], rax
0x18001dd26  test    rax, rax
0x18001dd29  jz      short loc_18001DD38
0x18001dd2b  mov     rcx, rax; this
0x18001dd2e  call    ??0CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::CSbSafeBuffer(void)
0x18001dd33  mov     rdx, rax
0x18001dd36  jmp     short loc_18001DD3A
0x18001dd38  xor     edx, edx
0x18001dd3a  mov     rax, [r14+100h]
0x18001dd41  mov     rcx, [rax]
0x18001dd44  mov     [rcx+rsi*8], rdx
0x18001dd48  mov     rdx, [r15]
0x18001dd4b  mov     rax, [r14+100h]
0x18001dd52  mov     rcx, [rax]
0x18001dd55  mov     rdx, [rdx+rsi*8]; struct CSbSafeBuffer *
0x18001dd59  mov     rcx, [rcx+rsi*8]; this
0x18001dd5d  call    ?CopyFromBuffer@CSbSafeBuffer@@QEAAJPEBV1@@Z; CSbSafeBuffer::CopyFromBuffer(CSbSafeBuffer const *)
0x18001dd62  mov     edi, eax
0x18001dd64  test    eax, eax
0x18001dd66  jns     short loc_18001DD95
0x18001dd68  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dd6f  cmp     rcx, r13
0x18001dd72  jz      short loc_18001DD93
0x18001dd74  cmp     byte ptr [rcx+19h], 2
0x18001dd78  jb      short loc_18001DD93
0x18001dd7a  mov     edx, 15h
0x18001dd7f  mov     r9d, eax
0x18001dd82  lea     r8, WPP_805ccd1b393d3e4b99a4efc8134fe3a0_Traceguids
0x18001dd89  mov     rcx, [rcx+10h]
0x18001dd8d  call    WPP_SF_d
0x18001dd92  nop
0x18001dd93  jmp     short loc_18001DDAD
0x18001dd95  inc     rsi
0x18001dd98  jmp     loc_18001DD00
0x18001dd9d  jmp     short loc_18001DDAD
0x18001dd9f  lea     r13, WPP_GLOBAL_Control
0x18001dda6  mov     edi, dword ptr [rsp+78h+arg_0]
0x18001ddad  mov     rcx, [rsp+78h+lpCriticalSection]; lpCriticalSection
0x18001ddb5  call    cs:__imp_LeaveCriticalSection
0x18001ddbb  mov     r10, cs:WPP_GLOBAL_Control
0x18001ddc2  cmp     r10, r13
0x18001ddc5  jz      short loc_18001DDF6
0x18001ddc7  test    edi, edi
0x18001ddc9  js      short loc_18001DDD2
0x18001ddcb  cmp     byte ptr [r10+19h], 6
0x18001ddd0  jb      short loc_18001DDF6
0x18001ddd2  or      ecx, 0FFFFFFFFh; int
0x18001ddd5  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001ddda  mov     edx, 17h
0x18001dddf  mov     [rsp+78h+var_58], edi
0x18001dde3  mov     r9, rax
0x18001dde6  lea     r8, WPP_805ccd1b393d3e4b99a4efc8134fe3a0_Traceguids
0x18001dded  mov     rcx, [r10+10h]
0x18001ddf1  call    WPP_SF_sd
0x18001ddf6  mov     eax, edi
0x18001ddf8  add     rsp, 48h
0x18001ddfc  pop     r15
0x18001ddfe  pop     r14
0x18001de00  pop     r13
0x18001de02  pop     r12
0x18001de04  pop     rdi
0x18001de05  pop     rsi
0x18001de06  retn
```
