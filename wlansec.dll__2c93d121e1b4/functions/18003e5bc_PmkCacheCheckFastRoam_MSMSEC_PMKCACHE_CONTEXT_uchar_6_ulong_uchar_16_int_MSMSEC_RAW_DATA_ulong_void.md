# PmkCacheCheckFastRoam(MSMSEC_PMKCACHE_CONTEXT *,uchar (*)[6],ulong,uchar (*)[16],int,MSMSEC_RAW_DATA *,ulong *,void * *)

- ea: `0x18003e5bc`
- end: `0x18003e9be`
- name: `?PmkCacheCheckFastRoam@@YAKPEAUMSMSEC_PMKCACHE_CONTEXT@@PEAY05EKPEAY0BA@EHPEAUMSMSEC_RAW_DATA@@PEAKPEAPEAX@Z`
- size: `1026`
- prototype: `unsigned int __usercall@<eax>(struct MSMSEC_PMKCACHE_CONTEXT *@<rcx>, unsigned __int8 (*)[6]@<rdx>, unsigned int@<r8d>, unsigned __int8 (*)[16]@<r9>, int, struct MSMSEC_RAW_DATA *, unsigned int *, void **)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x18002cb8c`

## callees

- `0x180006ae8`
- `0x1800083bc`
- `0x18000892c`
- `0x18000895c`
- `0x180008998`
- `0x18000bd78`
- `0x18000d5e4`
- `0x18001d370`
- `0x18001f29c`
- `0x18002eb78`
- `0x18002f430`
- `0x18003e5bc`
- `0x180043a30`
- `0x18006aa80`
- `0x18006ac08`

## import_xrefs

- `OneX!OneXCopyAuthParams` at `0x18003e83b`
- `OneX!OneXCopyAuthParams` at `0x18003e83b`
- `OneX!OneXFreeAuthParams` at `0x18003e925`
- `OneX!OneXFreeAuthParams` at `0x18003e925`

## pseudocode

```c
__int64 __fastcall PmkCacheCheckFastRoam(
        struct MSMSEC_PMKCACHE_CONTEXT *a1,
        unsigned __int8 (*a2)[6],
        unsigned int a3,
        unsigned __int8 (*a4)[16],
        int a5,
        struct MSMSEC_RAW_DATA *a6,
        unsigned int *a7,
        void **a8)
{
  __int64 v11; // r14
  __int64 v12; // r8
  PVOID *v13; // r9
  unsigned int PmkInfoForPeer; // ebx
  PVOID v15; // rcx
  __int64 v16; // rdx
  unsigned __int64 v17; // r14
  struct MSMSEC_RAW_DATA *v18; // rcx
  struct MSMSEC_RAW_DATA *v19; // rsi
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  void *v23; // [rsp+30h] [rbp-79h] BYREF
  struct MSMSEC_RAW_DATA *v24; // [rsp+38h] [rbp-71h] BYREF
  struct MSMSEC_RAW_DATA *v25; // [rsp+40h] [rbp-69h] BYREF
  unsigned __int64 v26; // [rsp+48h] [rbp-61h] BYREF
  __int128 v27; // [rsp+50h] [rbp-59h] BYREF
  void **v28; // [rsp+60h] [rbp-49h]
  unsigned __int8 *v29; // [rsp+70h] [rbp-39h]
  __int64 v30; // [rsp+78h] [rbp-31h]
  struct _EVENT_DATA_DESCRIPTOR v31; // [rsp+80h] [rbp-29h] BYREF
  unsigned __int8 v32[16]; // [rsp+90h] [rbp-19h] BYREF

  v28 = a8;
  *(_OWORD *)v32 = 0;
  v24 = 0;
  v25 = 0;
  v27 = 0;
  v23 = 0;
  v31 = 0;
  v26 = 0;
  v11 = a3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 225, &WPP_33279517f8f53e554228e3ed86a1217c_Traceguids);
  if ( !(unsigned int)IsPMKCacheValid(a1) )
  {
    if ( (byte_1800AED45 & 0x20) != 0 )
    {
      McGenEventWrite_EventWriteTransfer(
        &WLANSVC_EVT_GUID_Context,
        (const EVENT_DESCRIPTOR *)MsmSecPMKCacheInvalid,
        v12,
        1u,
        &v31);
      v13 = (PVOID *)WPP_GLOBAL_Control;
    }
    PmkInfoForPeer = 5023;
    if ( v13 == &WPP_GLOBAL_Control || (*((_BYTE *)v13 + 68) & 1) == 0 )
      goto LABEL_46;
    v15 = v13[7];
    v16 = 226;
    goto LABEL_10;
  }
  MSMSecLogBuffer(L"Checking for fast roam to MAC", (unsigned __int8 *)a2, 6u);
  if ( a5 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 227, &WPP_33279517f8f53e554228e3ed86a1217c_Traceguids);
    v17 = *((_QWORD *)a1 + 6);
    v18 = (struct MSMSEC_PMKCACHE_CONTEXT *)((char *)a1 + 80);
    v19 = (struct MSMSEC_PMKCACHE_CONTEXT *)((char *)a1 + 96);
LABEL_25:
    PmkInfoForPeer = CopyRawData(v18, &v27);
    if ( PmkInfoForPeer )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        v21 = 230;
        goto LABEL_45;
      }
    }
    else
    {
      if ( *(_DWORD *)v19 )
        CopyRawData(v19, &v31);
      PmkInfoForPeer = OneXCopyAuthParams(*((unsigned int *)a1 + 48), *((_QWORD *)a1 + 25), &v23);
      if ( PmkInfoForPeer )
      {
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          v21 = 231;
          goto LABEL_45;
        }
      }
      else
      {
        if ( (unsigned int)RawDataIsNonEmpty((char *)a1 + 80) )
          FreePrimaryAuth(a1);
        PmkInfoForPeer = SetPrimaryAuth(
                           a1,
                           a2,
                           (struct MSMSEC_RAW_DATA *)&v27,
                           (struct MSMSEC_RAW_DATA *)&v31,
                           (unsigned __int8 (*)[16])v32,
                           v17);
        if ( PmkInfoForPeer )
        {
          v20 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          {
            v21 = 232;
            goto LABEL_45;
          }
        }
        else
        {
          PmkInfoForPeer = SetPMKCacheTTLTimer(a1);
          if ( !PmkInfoForPeer )
          {
            *v28 = v23;
            *a7 = *((_DWORD *)a1 + 48);
            *((_QWORD *)a6 + 1) = *((_QWORD *)&v27 + 1);
            *(_DWORD *)a6 = v27;
            goto LABEL_49;
          }
          v20 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          {
            v21 = 233;
            goto LABEL_45;
          }
        }
      }
    }
    goto LABEL_46;
  }
  PmkInfoForPeer = GetPmkInfoForPeer(a1, a2, &v24, &v25, (unsigned __int8 (*)[16])v32, &v26);
  if ( !PmkInfoForPeer )
  {
    v29 = (unsigned __int8 *)a4;
    v30 = v11;
    if ( !(unsigned __int8)IsPmkIdCompatibleWithAssocRequest(v32) )
    {
      PmkInfoForPeer = 1168;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        v15 = (PVOID)*((_QWORD *)WPP_GLOBAL_Control + 7);
        v16 = 229;
LABEL_10:
        WPP_SF_(v15, v16, &WPP_33279517f8f53e554228e3ed86a1217c_Traceguids);
        goto LABEL_46;
      }
      goto LABEL_46;
    }
    v18 = v24;
    v19 = v25;
    v17 = v26;
    goto LABEL_25;
  }
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    v21 = 228;
LABEL_45:
    WPP_SF_d(v20[7], v21, &WPP_33279517f8f53e554228e3ed86a1217c_Traceguids, PmkInfoForPeer);
  }
LABEL_46:
  FreeRawData(&v27);
  if ( v23 )
  {
    OneXFreeAuthParams(v23);
    v23 = 0;
  }
LABEL_49:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 234, &WPP_33279517f8f53e554228e3ed86a1217c_Traceguids, PmkInfoForPeer);
  return PmkInfoForPeer;
}

```

## disassembly

```asm
0x18003e5bc  mov     [rsp-8+arg_10], rbx
0x18003e5c1  push    rbp
0x18003e5c2  push    rsi
0x18003e5c3  push    rdi
0x18003e5c4  push    r12
0x18003e5c6  push    r13
0x18003e5c8  push    r14
0x18003e5ca  push    r15
0x18003e5cc  lea     rbp, [rsp-7]
0x18003e5d1  sub     rsp, 0B0h
0x18003e5d8  mov     rax, cs:__security_cookie
0x18003e5df  xor     rax, rsp
0x18003e5e2  mov     [rbp+37h+var_40], rax
0x18003e5e6  mov     rax, [rbp+37h+arg_38]
0x18003e5ea  xor     ebx, ebx
0x18003e5ec  mov     r12, [rbp+37h+arg_28]
0x18003e5f0  xorps   xmm0, xmm0
0x18003e5f3  mov     r13, [rbp+37h+arg_30]
0x18003e5f7  xorps   xmm1, xmm1
0x18003e5fa  mov     [rbp+37h+var_80], rax
0x18003e5fe  mov     rsi, r9
0x18003e601  movups  xmmword ptr [rbp+37h+var_50], xmm0
0x18003e605  mov     [rbp+37h+var_A8], rbx
0x18003e609  mov     r15, rdx
0x18003e60c  mov     [rbp+37h+var_A0], rbx
0x18003e610  mov     rdi, rcx
0x18003e613  movups  [rbp+37h+var_90], xmm0
0x18003e617  mov     [rbp+37h+var_B0], rbx
0x18003e61b  movups  [rbp+37h+var_60], xmm1
0x18003e61f  mov     [rbp+37h+var_98], rbx
0x18003e623  mov     r14d, r8d
0x18003e626  mov     r9, cs:WPP_GLOBAL_Control
0x18003e62d  lea     rax, WPP_GLOBAL_Control
0x18003e634  cmp     r9, rax
0x18003e637  jz      short loc_18003E65F
0x18003e639  test    dword ptr [r9+44h], 100h
0x18003e641  jz      short loc_18003E65F
0x18003e643  mov     rcx, [r9+38h]
0x18003e647  lea     r8, WPP_33279517f8f53e554228e3ed86a1217c_Traceguids
0x18003e64e  mov     edx, 0E1h
0x18003e653  call    WPP_SF_
0x18003e658  mov     r9, cs:WPP_GLOBAL_Control
0x18003e65f  mov     rcx, rdi; struct MSMSEC_PMKCACHE_CONTEXT *
0x18003e662  call    ?IsPMKCacheValid@@YAHPEAUMSMSEC_PMKCACHE_CONTEXT@@@Z; IsPMKCacheValid(MSMSEC_PMKCACHE_CONTEXT *)
0x18003e667  test    eax, eax
0x18003e669  jnz     short loc_18003E6D7
0x18003e66b  test    cs:byte_1800AED45, 20h
0x18003e672  jz      short loc_18003E69D
0x18003e674  lea     rax, [rbp+37h+var_60]
0x18003e678  mov     r9d, 1
0x18003e67e  lea     rdx, MsmSecPMKCacheInvalid
0x18003e685  mov     [rsp+0E0h+var_C0], rax
0x18003e68a  lea     rcx, WLANSVC_EVT_GUID_Context
0x18003e691  call    McGenEventWrite_EventWriteTransfer
0x18003e696  mov     r9, cs:WPP_GLOBAL_Control
0x18003e69d  mov     ebx, 139Fh
0x18003e6a2  lea     rax, WPP_GLOBAL_Control
0x18003e6a9  cmp     r9, rax
0x18003e6ac  jz      loc_18003E913
0x18003e6b2  test    byte ptr [r9+44h], 1
0x18003e6b7  jz      loc_18003E913
0x18003e6bd  mov     rcx, [r9+38h]
0x18003e6c1  mov     edx, 0E2h
0x18003e6c6  lea     r8, WPP_33279517f8f53e554228e3ed86a1217c_Traceguids
0x18003e6cd  call    WPP_SF_
0x18003e6d2  jmp     loc_18003E913
0x18003e6d7  mov     r8d, 6; unsigned int
0x18003e6dd  lea     rcx, aCheckingForFas; "Checking for fast roam to MAC"
0x18003e6e4  mov     rdx, r15; unsigned __int8 *
0x18003e6e7  call    ?MSMSecLogBuffer@@YAXPEBGPEAEK@Z; MSMSecLogBuffer(ushort const *,uchar *,ulong)
0x18003e6ec  cmp     [rbp+37h+arg_20], ebx
0x18003e6ef  jz      short loc_18003E730
0x18003e6f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e6f8  lea     rax, WPP_GLOBAL_Control
0x18003e6ff  cmp     rcx, rax
0x18003e702  jz      short loc_18003E71F
0x18003e704  test    byte ptr [rcx+44h], 2
0x18003e708  jz      short loc_18003E71F
0x18003e70a  mov     rcx, [rcx+38h]
0x18003e70e  lea     r8, WPP_33279517f8f53e554228e3ed86a1217c_Traceguids
0x18003e715  mov     edx, 0E3h
0x18003e71a  call    WPP_SF_
0x18003e71f  mov     r14, [rdi+30h]
0x18003e723  lea     rcx, [rdi+50h]
0x18003e727  lea     rsi, [rdi+60h]
0x18003e72b  jmp     loc_18003E7DF
0x18003e730  lea     rax, [rbp+37h+var_98]
0x18003e734  mov     rdx, r15; unsigned __int8 (*)[6]
0x18003e737  mov     [rsp+0E0h+var_B8], rax; unsigned __int64 *
0x18003e73c  lea     r9, [rbp+37h+var_A0]; struct MSMSEC_RAW_DATA **
0x18003e740  lea     rax, [rbp+37h+var_50]
0x18003e744  mov     rcx, rdi; struct MSMSEC_PMKCACHE_CONTEXT *
0x18003e747  lea     r8, [rbp+37h+var_A8]; struct MSMSEC_RAW_DATA **
0x18003e74b  mov     [rsp+0E0h+var_C0], rax; unsigned __int8 (*)[16]
0x18003e750  call    ?GetPmkInfoForPeer@@YAKAEAUMSMSEC_PMKCACHE_CONTEXT@@PEAY05EPEAPEAUMSMSEC_RAW_DATA@@2PEAY0BA@EAEA_K@Z; GetPmkInfoForPeer(MSMSEC_PMKCACHE_CONTEXT &,uchar (*)[6],MSMSEC_RAW_DATA * *,MSMSEC_RAW_DATA * *,uchar (*)[16],unsigned __int64 &)
0x18003e755  mov     ebx, eax
0x18003e757  test    eax, eax
0x18003e759  jz      short loc_18003E786
0x18003e75b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e762  lea     rax, WPP_GLOBAL_Control
0x18003e769  cmp     rcx, rax
0x18003e76c  jz      loc_18003E913
0x18003e772  test    byte ptr [rcx+44h], 1
0x18003e776  jz      loc_18003E913
0x18003e77c  mov     edx, 0E4h
0x18003e781  jmp     loc_18003E900
0x18003e786  lea     rdx, [rbp+37h+var_70]
0x18003e78a  mov     [rbp+37h+var_70], rsi
0x18003e78e  lea     rcx, [rbp+37h+var_50]; unsigned __int8 *
0x18003e792  mov     [rbp+37h+var_68], r14
0x18003e796  call    ?IsPmkIdCompatibleWithAssocRequest@@YA_NAEAY0BA@$$CBEV?$span@$$BY0BA@$$CBE$0?0@utl@@@Z; IsPmkIdCompatibleWithAssocRequest(uchar const (&)[16],utl::span<uchar const [16],-1>)
0x18003e79b  test    al, al
0x18003e79d  jnz     short loc_18003E7D3
0x18003e79f  mov     ebx, 490h
0x18003e7a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e7ab  lea     rax, WPP_GLOBAL_Control
0x18003e7b2  cmp     rcx, rax
0x18003e7b5  jz      loc_18003E913
0x18003e7bb  test    byte ptr [rcx+44h], 1
0x18003e7bf  jz      loc_18003E913
0x18003e7c5  mov     rcx, [rcx+38h]
0x18003e7c9  mov     edx, 0E5h
0x18003e7ce  jmp     loc_18003E6C6
0x18003e7d3  mov     rcx, [rbp+37h+var_A8]
0x18003e7d7  mov     rsi, [rbp+37h+var_A0]
0x18003e7db  mov     r14, [rbp+37h+var_98]
0x18003e7df  lea     rdx, [rbp+37h+var_90]
0x18003e7e3  call    CopyRawData
0x18003e7e8  mov     ebx, eax
0x18003e7ea  test    eax, eax
0x18003e7ec  jz      short loc_18003E819
0x18003e7ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e7f5  lea     rax, WPP_GLOBAL_Control
0x18003e7fc  cmp     rcx, rax
0x18003e7ff  jz      loc_18003E913
0x18003e805  test    byte ptr [rcx+44h], 1
0x18003e809  jz      loc_18003E913
0x18003e80f  mov     edx, 0E6h
0x18003e814  jmp     loc_18003E900
0x18003e819  cmp     dword ptr [rsi], 0
0x18003e81c  jbe     short loc_18003E82A
0x18003e81e  lea     rdx, [rbp+37h+var_60]
0x18003e822  mov     rcx, rsi
0x18003e825  call    CopyRawData
0x18003e82a  mov     rdx, [rdi+0C8h]
0x18003e831  lea     r8, [rbp+37h+var_B0]
0x18003e835  mov     ecx, [rdi+0C0h]
0x18003e83b  call    cs:__imp_OneXCopyAuthParams
0x18003e842  nop     dword ptr [rax+rax+00h]
0x18003e847  mov     ebx, eax
0x18003e849  test    eax, eax
0x18003e84b  jz      short loc_18003E878
0x18003e84d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e854  lea     rax, WPP_GLOBAL_Control
0x18003e85b  cmp     rcx, rax
0x18003e85e  jz      loc_18003E913
0x18003e864  test    byte ptr [rcx+44h], 1
0x18003e868  jz      loc_18003E913
0x18003e86e  mov     edx, 0E7h
0x18003e873  jmp     loc_18003E900
0x18003e878  lea     rcx, [rdi+50h]
0x18003e87c  call    RawDataIsNonEmpty
0x18003e881  test    eax, eax
0x18003e883  jz      short loc_18003E88D
0x18003e885  mov     rcx, rdi; struct MSMSEC_PMKCACHE_CONTEXT *
0x18003e888  call    ?FreePrimaryAuth@@YAXPEAUMSMSEC_PMKCACHE_CONTEXT@@@Z; FreePrimaryAuth(MSMSEC_PMKCACHE_CONTEXT *)
0x18003e88d  lea     rax, [rbp+37h+var_50]
0x18003e891  mov     [rsp+0E0h+var_B8], r14; unsigned __int64
0x18003e896  lea     r9, [rbp+37h+var_60]; struct MSMSEC_RAW_DATA *
0x18003e89a  mov     [rsp+0E0h+var_C0], rax; unsigned __int8 (*)[16]
0x18003e89f  lea     r8, [rbp+37h+var_90]; struct MSMSEC_RAW_DATA *
0x18003e8a3  mov     rdx, r15; unsigned __int8 (*)[6]
0x18003e8a6  mov     rcx, rdi; struct MSMSEC_PMKCACHE_CONTEXT *
0x18003e8a9  call    ?SetPrimaryAuth@@YAKPEAUMSMSEC_PMKCACHE_CONTEXT@@PEAY05EPEAUMSMSEC_RAW_DATA@@2PEAY0BA@E_K@Z; SetPrimaryAuth(MSMSEC_PMKCACHE_CONTEXT *,uchar (*)[6],MSMSEC_RAW_DATA *,MSMSEC_RAW_DATA *,uchar (*)[16],unsigned __int64)
0x18003e8ae  mov     ebx, eax
0x18003e8b0  test    eax, eax
0x18003e8b2  jz      short loc_18003E8D4
0x18003e8b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e8bb  lea     rax, WPP_GLOBAL_Control
0x18003e8c2  cmp     rcx, rax
0x18003e8c5  jz      short loc_18003E913
0x18003e8c7  test    byte ptr [rcx+44h], 1
0x18003e8cb  jz      short loc_18003E913
0x18003e8cd  mov     edx, 0E8h
0x18003e8d2  jmp     short loc_18003E900
0x18003e8d4  mov     rcx, rdi; struct MSMSEC_PMKCACHE_CONTEXT *
0x18003e8d7  call    ?SetPMKCacheTTLTimer@@YAKPEAUMSMSEC_PMKCACHE_CONTEXT@@@Z; SetPMKCacheTTLTimer(MSMSEC_PMKCACHE_CONTEXT *)
0x18003e8dc  mov     ebx, eax
0x18003e8de  test    eax, eax
0x18003e8e0  jz      short loc_18003E93B
0x18003e8e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e8e9  lea     rax, WPP_GLOBAL_Control
0x18003e8f0  cmp     rcx, rax
0x18003e8f3  jz      short loc_18003E913
0x18003e8f5  test    byte ptr [rcx+44h], 1
0x18003e8f9  jz      short loc_18003E913
0x18003e8fb  mov     edx, 0E9h
0x18003e900  mov     rcx, [rcx+38h]
0x18003e904  lea     r8, WPP_33279517f8f53e554228e3ed86a1217c_Traceguids
0x18003e90b  mov     r9d, ebx
0x18003e90e  call    WPP_SF_d
0x18003e913  lea     rcx, [rbp+37h+var_90]
0x18003e917  call    FreeRawData
0x18003e91c  mov     rcx, [rbp+37h+var_B0]
0x18003e920  test    rcx, rcx
0x18003e923  jz      short loc_18003E960
0x18003e925  call    cs:__imp_OneXFreeAuthParams
0x18003e92c  nop     dword ptr [rax+rax+00h]
0x18003e931  mov     [rbp+37h+var_B0], 0
0x18003e939  jmp     short loc_18003E960
0x18003e93b  mov     rax, [rbp+37h+var_B0]
0x18003e93f  mov     rcx, [rbp+37h+var_80]
0x18003e943  mov     [rcx], rax
0x18003e946  mov     eax, [rdi+0C0h]
0x18003e94c  mov     [r13+0], eax
0x18003e950  mov     rax, qword ptr [rbp+37h+var_90+8]
0x18003e954  mov     [r12+8], rax
0x18003e959  mov     eax, dword ptr [rbp+37h+var_90]
0x18003e95c  mov     [r12], eax
0x18003e960  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e967  lea     rax, WPP_GLOBAL_Control
0x18003e96e  cmp     rcx, rax
0x18003e971  jz      short loc_18003E994
0x18003e973  test    dword ptr [rcx+44h], 100h
0x18003e97a  jz      short loc_18003E994
0x18003e97c  mov     rcx, [rcx+38h]
0x18003e980  lea     r8, WPP_33279517f8f53e554228e3ed86a1217c_Traceguids
0x18003e987  mov     edx, 0EAh
0x18003e98c  mov     r9d, ebx
0x18003e98f  call    WPP_SF_d
0x18003e994  mov     eax, ebx
0x18003e996  mov     rcx, [rbp+37h+var_40]
0x18003e99a  xor     rcx, rsp; StackCookie
0x18003e99d  call    __security_check_cookie
0x18003e9a2  mov     rbx, [rsp+0E0h+arg_10]
0x18003e9aa  add     rsp, 0B0h
0x18003e9b1  pop     r15
0x18003e9b3  pop     r14
0x18003e9b5  pop     r13
0x18003e9b7  pop     r12
0x18003e9b9  pop     rdi
0x18003e9ba  pop     rsi
0x18003e9bb  pop     rbp
0x18003e9bc  retn
```
