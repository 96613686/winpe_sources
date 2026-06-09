# CSsdpCacheEntryManager::HrUpdateCacheList(_SSDP_REQUEST *,int)

- ea: `0x180003a00`
- end: `0x180003f7b`
- name: `?HrUpdateCacheList@CSsdpCacheEntryManager@@QEAAJPEAU_SSDP_REQUEST@@H@Z`
- size: `1403`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, struct _SSDP_REQUEST *, int)`
- caller_count: `2`
- callee_count: `17`
- tags: `installer_update`

## callers

- `0x1800029b0`
- `0x180005d90`

## callees

- `0x180003a00`
- `0x180005740`
- `0x18000993c`
- `0x180009bc0`
- `0x18000a590`
- `0x180015c78`
- `0x180016384`
- `0x1800186a0`
- `0x18001b070`
- `0x1800203f8`
- `0x180021c90`
- `0x180022a80`
- `0x18002482c`
- `0x1800255a8`
- `0x180028000`
- `0x18002f028`
- `0x180035274`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180003ead`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180003f70`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180003ead`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180003f70`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180003d2a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180003d2a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003aaa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003c29`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003c8a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003d1f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003d56`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003aaa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003c29`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003c8a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003d1f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003d56`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003a96`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003b5d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003c05`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003d0d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003a96`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003b5d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003c05`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003d0d`

## pseudocode

```c
__int64 __fastcall CSsdpCacheEntryManager::HrUpdateCacheList(
        LPCRITICAL_SECTION lpCriticalSection,
        struct _SSDP_REQUEST *a2,
        int a3)
{
  int v3; // esi
  int v4; // edi
  struct _SSDP_REQUEST *v5; // r12
  struct _RTL_CRITICAL_SECTION *v6; // rax
  _QWORD *v7; // rbx
  const char *v8; // rcx
  struct _RTL_CRITICAL_SECTION *v9; // rcx
  int appended; // r13d
  int v11; // esi
  void *v12; // rbx
  struct _RTL_CRITICAL_SECTION *v14; // rax
  bool v15; // zf
  LPCRITICAL_SECTION v16; // r14
  LPCRITICAL_SECTION v17; // rbx
  int v18; // edi
  unsigned __int8 *v19; // rcx
  unsigned __int8 i; // al
  __int64 p_CriticalSection; // r15
  __int64 v22; // r14
  __int64 v23; // rax
  unsigned __int8 *v24; // rax
  __int64 v25; // r14
  int v26; // edx
  int v27; // esi
  int updated; // eax
  struct _NETWORK_LOCATION_INFO **v29; // rax
  struct _NETWORK_LOCATION_INFO **v30; // rbx
  _QWORD *v31; // rcx
  PRTL_CRITICAL_SECTION_DEBUG *v32; // rdx
  LPCRITICAL_SECTION v33; // rcx
  struct _RTL_CRITICAL_SECTION *v34; // rbx
  int v35; // eax
  int v36; // [rsp+38h] [rbp-19h]
  int v37; // [rsp+3Ch] [rbp-15h] BYREF
  unsigned int v38; // [rsp+40h] [rbp-11h] BYREF
  int v39; // [rsp+44h] [rbp-Dh] BYREF
  LPCRITICAL_SECTION v40; // [rsp+48h] [rbp-9h]
  void *Block; // [rsp+50h] [rbp-1h] BYREF
  struct _RTL_CRITICAL_SECTION *v42; // [rsp+58h] [rbp+7h] BYREF
  LPCRITICAL_SECTION lpCriticalSectiona; // [rsp+B8h] [rbp+67h] BYREF
  struct _SSDP_REQUEST *p_Block; // [rsp+C0h] [rbp+6Fh] BYREF
  int v45; // [rsp+C8h] [rbp+77h]
  int v46; // [rsp+D0h] [rbp+7Fh]

  v45 = a3;
  p_Block = a2;
  lpCriticalSectiona = lpCriticalSection;
  v3 = 0;
  v4 = a3;
  v5 = a2;
  v6 = lpCriticalSection;
  v36 = 0;
  v38 = 0;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
  {
    WPP_SF_qd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      66,
      WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids,
      lpCriticalSection,
      a3);
    v6 = lpCriticalSectiona;
  }
  v7 = (_QWORD *)*((_QWORD *)v5 + 10);
  v46 = 0;
  v37 = 0;
  v39 = 0;
  Block = 0;
  v8 = (const char *)v7[2];
  if ( v8 )
  {
    if ( !strcmp_0(v8, "ssdp:byebye") )
    {
      v9 = lpCriticalSectiona;
      v3 = 1;
      v36 = 1;
      appended = 0;
      goto LABEL_17;
    }
    v6 = lpCriticalSectiona;
  }
  v9 = v6;
  if ( !v7[9] || (appended = 0, !v7[17]) )
  {
    appended = 1;
    EnterCriticalSection(v6);
    v11 = v46;
    goto LABEL_6;
  }
LABEL_17:
  EnterCriticalSection(v9);
  v14 = lpCriticalSectiona;
  v15 = lpCriticalSectiona[1].DebugInfo == 0;
  v16 = lpCriticalSectiona + 1;
  v17 = lpCriticalSectiona + 1;
  v40 = lpCriticalSectiona + 1;
  v42 = lpCriticalSectiona + 1;
  if ( !v15 )
  {
    v18 = 0;
    v19 = *(unsigned __int8 **)(*((_QWORD *)v5 + 10) + 64LL);
    for ( i = *v19; *v19; i = *v19 )
    {
      ++v19;
      v18 = i + 101 * v18;
    }
    while ( 1 )
    {
      if ( !v17 || !v17->DebugInfo )
      {
LABEL_21:
        v4 = v45;
        v16 = v40;
        v3 = v36;
        v14 = lpCriticalSectiona;
        break;
      }
      p_CriticalSection = (__int64)&v17->DebugInfo->CriticalSection;
      v22 = *(_QWORD *)(*((_QWORD *)v5 + 10) + 64LL);
      EnterCriticalSection((LPCRITICAL_SECTION)&v17->DebugInfo[4].EntryCount);
      if ( v22
        && (v23 = *(_QWORD *)(p_CriticalSection + 88)) != 0
        && (v24 = *(unsigned __int8 **)(v23 + 64)) != 0
        && v18 == *(_DWORD *)(p_CriticalSection + 256) )
      {
        v25 = v22 - (_QWORD)v24;
        do
        {
          v26 = v24[v25];
          v27 = *v24 - v26;
          if ( v27 )
            break;
          ++v24;
        }
        while ( v26 );
        LeaveCriticalSection((LPCRITICAL_SECTION)(p_CriticalSection + 216));
        if ( !v27 )
        {
          if ( v36 )
          {
            CUList<CSsdpCacheEntry>::Iterator::HrMoveToList((_QWORD ***)&v42, &Block);
            --lpCriticalSectiona[1].LockCount;
            if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                67,
                WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids,
                (unsigned int)lpCriticalSectiona[1].LockCount);
            v11 = v46;
            v5 = p_Block;
          }
          else
          {
            v5 = p_Block;
            updated = CSsdpCacheEntry::HrUpdateEntry((CSsdpCacheEntry *)p_CriticalSection, p_Block, &v39, &v37, &v38);
            v11 = v37;
            appended = updated;
            if ( !updated && v37 )
              appended = CSsdpCacheEntry::HrAppendNetworkInfoToRequest((CSsdpCacheEntry *)p_CriticalSection, v5);
          }
          goto LABEL_6;
        }
      }
      else
      {
        LeaveCriticalSection((LPCRITICAL_SECTION)(p_CriticalSection + 216));
      }
      v17 = (LPCRITICAL_SECTION)v17->DebugInfo;
      v5 = p_Block;
      if ( v17 )
      {
        v15 = v17->DebugInfo == 0;
        v42 = v17;
        if ( !v15 )
          continue;
      }
      goto LABEL_21;
    }
  }
  if ( v3 || !v4 )
  {
LABEL_23:
    v11 = v46;
    goto LABEL_6;
  }
  EnterCriticalSection(v14);
  if ( lpCriticalSectiona[1].LockCount >= lpCriticalSectiona[1].RecursionCount )
  {
    LeaveCriticalSection(lpCriticalSectiona);
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids);
    goto LABEL_23;
  }
  LeaveCriticalSection(lpCriticalSectiona);
  v29 = (struct _NETWORK_LOCATION_INFO **)malloc(0x118u);
  v30 = v29;
  if ( !v29 )
  {
    v11 = v46;
    appended = -2147024882;
    goto LABEL_6;
  }
  *v29 = 0;
  CSsdpCacheEntry::CSsdpCacheEntry((CSsdpCacheEntry *)(v29 + 1));
  *v30 = 0;
  appended = CSsdpCacheEntry::HrInitialize(v30 + 1, v5);
  if ( appended < 0
    || (appended = CSsdpCacheEntry::HrAppendNetworkInfoToRequest((CSsdpCacheEntry *)(v30 + 1), v5), appended < 0) )
  {
    v11 = v46;
    goto LABEL_63;
  }
  v11 = 1;
  v38 = 1;
  appended = CSsdpCacheEntry::HrStartTimer((CSsdpCacheEntry *)(v30 + 1), v5);
  if ( appended < 0 )
  {
LABEL_63:
    CUList<CSsdpCacheEntry>::Node::~Node((_QWORD **)v30);
    free(v30);
    goto LABEL_6;
  }
  v31 = v30;
  do
  {
    v32 = (PRTL_CRITICAL_SECTION_DEBUG *)v31;
    v31 = (_QWORD *)*v31;
  }
  while ( v31 );
  v33 = lpCriticalSectiona;
  *v32 = v16->DebugInfo;
  v16->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)v30;
  ++v33[1].LockCount;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      68,
      WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids,
      (unsigned int)lpCriticalSectiona[1].LockCount);
LABEL_6:
  LeaveCriticalSection(lpCriticalSectiona);
  if ( v11 )
    CSsdpNotifyRequestManager::HrCheckListNotifyForAliveOrByebye(&CSsdpNotifyRequestManager::s_instance, v5, v39, v38);
  p_Block = (struct _SSDP_REQUEST *)&Block;
  if ( Block )
  {
    lpCriticalSectiona = 0;
    do
    {
      if ( (unsigned int)CUList<CRundownHelperBase *>::Iterator::HrGetItem((__int64 **)&p_Block, &lpCriticalSectiona) )
        break;
      v34 = lpCriticalSectiona;
      v35 = CSsdpCacheEntry::NotifyByeByeForAllAddressFamily((CSsdpCacheEntry *)lpCriticalSectiona);
      if ( v35 < 0 && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          70,
          WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids,
          (unsigned int)v35);
      appended = CSsdpCacheEntry::HrShutdown(v34, 0);
    }
    while ( !(unsigned int)CUList<__int64>::Iterator::HrNext((_QWORD ***)&p_Block) );
  }
  if ( appended && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      71,
      WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids,
      (unsigned int)appended);
  v12 = Block;
  if ( Block )
  {
    CUList<CSsdpCacheEntry>::Node::~Node((_QWORD **)Block);
    free(v12);
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180003a00  mov     rax, rsp
0x180003a03  mov     [rax+18h], r8d
0x180003a07  mov     [rax+10h], rdx
0x180003a0b  mov     [rax+8], rcx
0x180003a0f  push    rbp
0x180003a10  push    rbx
0x180003a11  push    r13
0x180003a13  lea     rbp, [rax-5Fh]
0x180003a17  sub     rsp, 90h
0x180003a1e  mov     [rax-20h], rsi
0x180003a22  xor     esi, esi
0x180003a24  mov     [rax-28h], rdi
0x180003a28  mov     edi, r8d
0x180003a2b  mov     [rax-30h], r12
0x180003a2f  mov     r12, rdx
0x180003a32  mov     [rax-40h], r15
0x180003a36  mov     rax, rcx
0x180003a39  mov     [rbp+57h+var_70], esi
0x180003a3c  mov     [rbp+57h+var_68], esi
0x180003a3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180003a46  lea     r15, WPP_GLOBAL_Control
0x180003a4d  cmp     rcx, r15
0x180003a50  jnz     loc_180003B0A
0x180003a56  mov     rbx, [r12+50h]
0x180003a5b  xor     ecx, ecx
0x180003a5d  mov     [rbp+57h+arg_18], ecx
0x180003a60  mov     [rbp+57h+var_6C], ecx
0x180003a63  mov     [rbp+57h+var_64], ecx
0x180003a66  mov     [rbp+57h+Block], rcx
0x180003a6a  mov     rcx, [rbx+10h]; Str1
0x180003a6e  test    rcx, rcx
0x180003a71  jnz     loc_180003B3A
0x180003a77  mov     rcx, rax; lpCriticalSection
0x180003a7a  cmp     [rbx+48h], rsi
0x180003a7e  jz      short loc_180003A90
0x180003a80  xor     r13d, r13d
0x180003a83  cmp     [rbx+88h], rsi
0x180003a8a  jnz     loc_180003B5D
0x180003a90  mov     r13d, 1
0x180003a96  call    cs:__imp_EnterCriticalSection
0x180003a9c  mov     esi, [rbp+57h+arg_18]
0x180003a9f  lea     rdi, WPP_GLOBAL_Control
0x180003aa6  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x180003aaa  call    cs:__imp_LeaveCriticalSection
0x180003ab0  mov     r15, [rsp+0A0h+var_38]
0x180003ab5  test    esi, esi
0x180003ab7  mov     rsi, qword ptr [rsp+0A0h+var_18]
0x180003abf  jnz     loc_180003CE6
0x180003ac5  cmp     [rbp+57h+Block], 0
0x180003aca  lea     rax, [rbp+57h+Block]
0x180003ace  mov     r12, [rsp+0A0h+var_28]
0x180003ad3  mov     [rbp+57h+arg_8], rax
0x180003ad7  jnz     loc_180003EB8
0x180003add  test    r13d, r13d
0x180003ae0  jnz     loc_180003F2E
0x180003ae6  mov     rbx, [rbp+57h+Block]
0x180003aea  mov     rdi, [rsp+0A0h+var_20]
0x180003af2  test    rbx, rbx
0x180003af5  jnz     loc_180003F65
0x180003afb  mov     eax, r13d
0x180003afe  add     rsp, 90h
0x180003b05  pop     r13
0x180003b07  pop     rbx
0x180003b08  pop     rbp
0x180003b09  retn
0x180003b0a  test    byte ptr [rcx+1Ch], 8
0x180003b0e  jz      loc_180003A56
0x180003b14  mov     rcx, [rcx+10h]
0x180003b18  mov     edx, 42h ; 'B'
0x180003b1d  mov     [rsp+20h], r8d
0x180003b22  mov     r9, rax
0x180003b25  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180003b2c  call    WPP_SF_qd
0x180003b31  mov     rax, [rbp+57h+lpCriticalSection]
0x180003b35  jmp     loc_180003A56
0x180003b3a  lea     rdx, aSsdpByebye; "ssdp:byebye"
0x180003b41  call    strcmp_0
0x180003b46  test    eax, eax
0x180003b48  jnz     loc_180003C52
0x180003b4e  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x180003b52  mov     esi, 1
0x180003b57  mov     [rbp+57h+var_70], esi
0x180003b5a  xor     r13d, r13d
0x180003b5d  call    cs:__imp_EnterCriticalSection
0x180003b63  mov     rax, [rbp+57h+lpCriticalSection]
0x180003b67  cmp     qword ptr [rax+28h], 0
0x180003b6c  mov     [rsp+0A0h+var_30], r14
0x180003b71  lea     r14, [rax+28h]
0x180003b75  mov     rbx, r14
0x180003b78  mov     [rbp+57h+var_60], r14
0x180003b7c  mov     [rbp+57h+var_50], rbx
0x180003b80  jz      short loc_180003BCD
0x180003b82  mov     rax, [r12+50h]
0x180003b87  xor     edi, edi
0x180003b89  mov     rcx, [rax+40h]
0x180003b8d  movzx   eax, byte ptr [rcx]
0x180003b90  test    al, al
0x180003b92  jz      short loc_180003BB3
0x180003b94  nop     dword ptr [rax+00h]
0x180003b98  nop     dword ptr [rax+rax+00000000h]
0x180003ba0  imul    edi, 65h ; 'e'
0x180003ba3  lea     rcx, [rcx+1]
0x180003ba7  movzx   eax, al
0x180003baa  add     edi, eax
0x180003bac  movzx   eax, byte ptr [rcx]
0x180003baf  test    al, al
0x180003bb1  jnz     short loc_180003BA0
0x180003bb3  test    rbx, rbx
0x180003bb6  jnz     short loc_180003BE9
0x180003bb8  mov     edi, [rbp+57h+arg_10]
0x180003bbb  lea     r15, WPP_GLOBAL_Control
0x180003bc2  mov     r14, [rbp+57h+var_60]
0x180003bc6  mov     esi, [rbp+57h+var_70]
0x180003bc9  mov     rax, [rbp+57h+lpCriticalSection]
0x180003bcd  test    esi, esi
0x180003bcf  jz      loc_180003D02
0x180003bd5  mov     esi, [rbp+57h+arg_18]
0x180003bd8  lea     rdi, WPP_GLOBAL_Control
0x180003bdf  mov     r14, [rsp+0A0h+var_30]
0x180003be4  jmp     loc_180003AA6
0x180003be9  mov     rax, [rbx]
0x180003bec  test    rax, rax
0x180003bef  jz      short loc_180003BB8
0x180003bf1  lea     r15, [rax+8]
0x180003bf5  mov     rax, [r12+50h]
0x180003bfa  lea     rcx, [r15+0D8h]; lpCriticalSection
0x180003c01  mov     r14, [rax+40h]
0x180003c05  call    cs:__imp_EnterCriticalSection
0x180003c0b  test    r14, r14
0x180003c0e  jz      short loc_180003C22
0x180003c10  mov     rax, [r15+58h]
0x180003c14  test    rax, rax
0x180003c17  jz      short loc_180003C22
0x180003c19  mov     rax, [rax+40h]
0x180003c1d  test    rax, rax
0x180003c20  jnz     short loc_180003C5B
0x180003c22  lea     rcx, [r15+0D8h]; lpCriticalSection
0x180003c29  call    cs:__imp_LeaveCriticalSection
0x180003c2f  mov     rbx, [rbx]
0x180003c32  mov     r12, [rbp+57h+arg_8]
0x180003c36  test    rbx, rbx
0x180003c39  jz      loc_180003BB8
0x180003c3f  cmp     qword ptr [rbx], 0
0x180003c43  mov     [rbp+57h+var_50], rbx
0x180003c47  jnz     loc_180003BB3
0x180003c4d  jmp     loc_180003BB8
0x180003c52  mov     rax, [rbp+57h+lpCriticalSection]
0x180003c56  jmp     loc_180003A77
0x180003c5b  cmp     edi, [r15+100h]
0x180003c62  jnz     short loc_180003C22
0x180003c64  sub     r14, rax
0x180003c67  nop     word ptr [rax+rax+00000000h]
0x180003c70  movzx   esi, byte ptr [rax]
0x180003c73  movzx   edx, byte ptr [rax+r14]
0x180003c78  sub     esi, edx
0x180003c7a  jnz     short loc_180003C83
0x180003c7c  inc     rax
0x180003c7f  test    edx, edx
0x180003c81  jnz     short loc_180003C70
0x180003c83  lea     rcx, [r15+0D8h]; lpCriticalSection
0x180003c8a  call    cs:__imp_LeaveCriticalSection
0x180003c90  test    esi, esi
0x180003c92  jnz     short loc_180003C2F
0x180003c94  cmp     [rbp+57h+var_70], esi
0x180003c97  jnz     loc_180003D90
0x180003c9d  mov     r12, [rbp+57h+arg_8]
0x180003ca1  lea     rax, [rbp+57h+var_68]
0x180003ca5  mov     rdx, r12; struct _SSDP_REQUEST *
0x180003ca8  mov     [rsp+20h], rax; unsigned int *
0x180003cad  lea     r9, [rbp+57h+var_6C]; int *
0x180003cb1  mov     rcx, r15; this
0x180003cb4  lea     r8, [rbp+57h+var_64]; int *
0x180003cb8  call    ?HrUpdateEntry@CSsdpCacheEntry@@QEAAJPEBU_SSDP_REQUEST@@PEAH1PEAK@Z; CSsdpCacheEntry::HrUpdateEntry(_SSDP_REQUEST const *,int *,int *,ulong *)
0x180003cbd  mov     esi, [rbp+57h+var_6C]
0x180003cc0  mov     r13d, eax
0x180003cc3  test    eax, eax
0x180003cc5  jnz     loc_180003BD8
0x180003ccb  test    esi, esi
0x180003ccd  jz      loc_180003BD8
0x180003cd3  mov     rdx, r12; struct _SSDP_REQUEST *
0x180003cd6  mov     rcx, r15; this
0x180003cd9  call    ?HrAppendNetworkInfoToRequest@CSsdpCacheEntry@@QEAAJPEAU_SSDP_REQUEST@@@Z; CSsdpCacheEntry::HrAppendNetworkInfoToRequest(_SSDP_REQUEST *)
0x180003cde  mov     r13d, eax
0x180003ce1  jmp     loc_180003BD8
0x180003ce6  mov     r9d, [rbp+57h+var_68]; unsigned int
0x180003cea  lea     rcx, ?s_instance@CSsdpNotifyRequestManager@@0V1@A; lpCriticalSection
0x180003cf1  mov     r8d, [rbp+57h+var_64]; int
0x180003cf5  mov     rdx, r12; struct _SSDP_REQUEST *
0x180003cf8  call    ?HrCheckListNotifyForAliveOrByebye@CSsdpNotifyRequestManager@@QEAAJPEBU_SSDP_REQUEST@@HK@Z; CSsdpNotifyRequestManager::HrCheckListNotifyForAliveOrByebye(_SSDP_REQUEST const *,int,ulong)
0x180003cfd  jmp     loc_180003AC5
0x180003d02  test    edi, edi
0x180003d04  jz      loc_180003BD5
0x180003d0a  mov     rcx, rax; lpCriticalSection
0x180003d0d  call    cs:__imp_EnterCriticalSection
0x180003d13  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x180003d17  mov     eax, [rcx+34h]
0x180003d1a  cmp     [rcx+30h], eax
0x180003d1d  jge     short loc_180003D56
0x180003d1f  call    cs:__imp_LeaveCriticalSection
0x180003d25  mov     ecx, 118h; Size
0x180003d2a  call    cs:__imp_malloc
0x180003d30  mov     rbx, rax
0x180003d33  test    rax, rax
0x180003d36  jnz     loc_180003DE6
0x180003d3c  mov     esi, [rbp+57h+arg_18]
0x180003d3f  lea     rdi, WPP_GLOBAL_Control
0x180003d46  mov     r14, [rsp+0A0h+var_30]
0x180003d4b  mov     r13d, 8007000Eh
0x180003d51  jmp     loc_180003AA6
0x180003d56  call    cs:__imp_LeaveCriticalSection
0x180003d5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d63  cmp     rcx, r15
0x180003d66  jz      loc_180003BD5
0x180003d6c  test    byte ptr [rcx+1Ch], 8
0x180003d70  jz      loc_180003BD5
0x180003d76  mov     rcx, [rcx+10h]
0x180003d7a  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180003d81  mov     edx, 45h ; 'E'
0x180003d86  call    WPP_SF_
0x180003d8b  jmp     loc_180003BD5
0x180003d90  lea     rdx, [rbp+57h+Block]
0x180003d94  lea     rcx, [rbp+57h+var_50]
0x180003d98  call    ?HrMoveToList@Iterator@?$CUList@VCSsdpCacheEntry@@@@QEAAJAEAV2@@Z; CUList<CSsdpCacheEntry>::Iterator::HrMoveToList(CUList<CSsdpCacheEntry> &)
0x180003d9d  mov     rcx, [rbp+57h+lpCriticalSection]
0x180003da1  dec     dword ptr [rcx+30h]
0x180003da4  mov     rcx, cs:WPP_GLOBAL_Control
0x180003dab  lea     rdi, WPP_GLOBAL_Control
0x180003db2  cmp     rcx, rdi
0x180003db5  jz      short loc_180003DDA
0x180003db7  test    byte ptr [rcx+1Ch], 8
0x180003dbb  jz      short loc_180003DDA
0x180003dbd  mov     rax, [rbp+57h+lpCriticalSection]
0x180003dc1  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180003dc8  mov     rcx, [rcx+10h]
0x180003dcc  mov     edx, 43h ; 'C'
0x180003dd1  mov     r9d, [rax+30h]
0x180003dd5  call    WPP_SF_d
0x180003dda  mov     esi, [rbp+57h+arg_18]
0x180003ddd  mov     r12, [rbp+57h+arg_8]
0x180003de1  jmp     loc_180003BDF
0x180003de6  lea     rcx, [rax+8]; this
0x180003dea  mov     qword ptr [rax], 0
0x180003df1  call    ??0CSsdpCacheEntry@@QEAA@XZ; CSsdpCacheEntry::CSsdpCacheEntry(void)
0x180003df6  mov     rdx, r12; struct _SSDP_REQUEST *
0x180003df9  mov     qword ptr [rbx], 0
0x180003e00  lea     rcx, [rbx+8]; this
0x180003e04  call    ?HrInitialize@CSsdpCacheEntry@@QEAAJPEBU_SSDP_REQUEST@@@Z; CSsdpCacheEntry::HrInitialize(_SSDP_REQUEST const *)
0x180003e09  mov     r13d, eax
0x180003e0c  test    eax, eax
0x180003e0e  js      loc_180003E9F
0x180003e14  mov     rdx, r12; struct _SSDP_REQUEST *
0x180003e17  lea     rcx, [rbx+8]; this
0x180003e1b  call    ?HrAppendNetworkInfoToRequest@CSsdpCacheEntry@@QEAAJPEAU_SSDP_REQUEST@@@Z; CSsdpCacheEntry::HrAppendNetworkInfoToRequest(_SSDP_REQUEST *)
0x180003e20  mov     r13d, eax
0x180003e23  test    eax, eax
0x180003e25  js      short loc_180003E9F
0x180003e27  mov     esi, 1
0x180003e2c  lea     rcx, [rbx+8]; this
0x180003e30  mov     rdx, r12; struct _SSDP_REQUEST *
0x180003e33  mov     [rbp+57h+var_68], esi
0x180003e36  call    ?HrStartTimer@CSsdpCacheEntry@@QEAAJPEBU_SSDP_REQUEST@@@Z; CSsdpCacheEntry::HrStartTimer(_SSDP_REQUEST const *)
0x180003e3b  mov     r13d, eax
0x180003e3e  test    eax, eax
0x180003e40  js      short loc_180003EA2
0x180003e42  mov     rcx, rbx
0x180003e45  mov     rax, [rcx]
0x180003e48  lea     rdx, [rcx]
0x180003e4b  mov     rcx, rax
0x180003e4e  test    rax, rax
0x180003e51  jnz     short loc_180003E45
0x180003e53  mov     rax, [r14]
0x180003e56  mov     rcx, [rbp+57h+lpCriticalSection]
0x180003e5a  mov     [rdx], rax
0x180003e5d  mov     [r14], rbx
0x180003e60  inc     dword ptr [rcx+30h]
0x180003e63  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e6a  cmp     rcx, r15
0x180003e6d  jz      loc_180003BD8
0x180003e73  test    byte ptr [rcx+1Ch], 8
0x180003e77  jz      loc_180003BD8
0x180003e7d  mov     rax, [rbp+57h+lpCriticalSection]
0x180003e81  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180003e88  mov     rcx, [rcx+10h]
0x180003e8c  mov     edx, 44h ; 'D'
0x180003e91  mov     r9d, [rax+30h]
0x180003e95  call    WPP_SF_d
0x180003e9a  jmp     loc_180003BD8
0x180003e9f  mov     esi, [rbp+57h+arg_18]
0x180003ea2  mov     rcx, rbx
0x180003ea5  call    ??1Node@?$CUList@VCSsdpCacheEntry@@@@QEAA@XZ; CUList<CSsdpCacheEntry>::Node::~Node(void)
0x180003eaa  mov     rcx, rbx; Block
0x180003ead  call    cs:__imp_free
0x180003eb3  jmp     loc_180003BD8
0x180003eb8  mov     [rbp+57h+lpCriticalSection], 0
0x180003ec0  lea     rdx, [rbp+57h+lpCriticalSection]
0x180003ec4  lea     rcx, [rbp+57h+arg_8]
0x180003ec8  call    ?HrGetItem@Iterator@?$CUList@PEAVCRundownHelperBase@@@@QEAAJPEAPEAPEAVCRundownHelperBase@@@Z; CUList<CRundownHelperBase *>::Iterator::HrGetItem(CRundownHelperBase * * *)
0x180003ecd  test    eax, eax
0x180003ecf  jnz     loc_180003ADD
0x180003ed5  mov     rbx, [rbp+57h+lpCriticalSection]
  ... truncated ...
```
