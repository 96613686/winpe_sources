# CSsdpCacheEntryManager::HrUpdateCacheList(_SSDP_REQUEST *,int)

- ea: `0x180005260`
- end: `0x180005804`
- name: `?HrUpdateCacheList@CSsdpCacheEntryManager@@QEAAJPEAU_SSDP_REQUEST@@H@Z`
- size: `1444`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, struct _SSDP_REQUEST *, int)`
- caller_count: `2`
- callee_count: `18`
- tags: `installer_update`

## callers

- `0x1800040e0`
- `0x1800070d0`

## callees

- `0x180005260`
- `0x180006a60`
- `0x18000aef4`
- `0x18000b184`
- `0x18000baf8`
- `0x18000bd3c`
- `0x1800198bc`
- `0x180019920`
- `0x18001c374`
- `0x1800209e0`
- `0x180021c54`
- `0x180023484`
- `0x180024490`
- `0x180026344`
- `0x1800271fc`
- `0x180029df0`
- `0x180031278`
- `0x180037db4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800055cf`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800057f3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800055cf`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800057f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005314`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800054a0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800054fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005314`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800054a0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800054fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800052f6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800053cf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005476`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800052f6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800053cf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005476`

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
  struct _RTL_CRITICAL_SECTION *v11; // rsi
  int v12; // r14d
  void *v13; // rbx
  LPCRITICAL_SECTION v15; // r15
  LPCRITICAL_SECTION v16; // rbx
  int v17; // edi
  unsigned __int8 *v18; // rcx
  unsigned __int8 i; // al
  bool v20; // zf
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rax
  struct _RTL_CRITICAL_SECTION **p_CriticalSection; // r15
  __int64 v23; // r14
  struct _RTL_CRITICAL_SECTION *v24; // rax
  unsigned __int8 *LockSemaphore; // rax
  __int64 v26; // r14
  int v27; // edx
  int v28; // esi
  int updated; // eax
  int v30; // eax
  void **v31; // rbx
  void **p_Block; // rcx
  LPCRITICAL_SECTION v33; // rcx
  CSsdpCacheEntry *v34; // rbx
  int v35; // eax
  int v36; // [rsp+38h] [rbp-19h]
  int v37; // [rsp+3Ch] [rbp-15h] BYREF
  unsigned int v38; // [rsp+40h] [rbp-11h] BYREF
  int v39; // [rsp+44h] [rbp-Dh] BYREF
  LPCRITICAL_SECTION v40; // [rsp+48h] [rbp-9h]
  void *v41; // [rsp+50h] [rbp-1h] BYREF
  LPCRITICAL_SECTION v42[2]; // [rsp+58h] [rbp+7h] BYREF
  LPCRITICAL_SECTION lpCriticalSectiona; // [rsp+B8h] [rbp+67h] BYREF
  void *Block; // [rsp+C0h] [rbp+6Fh] BYREF
  int v45; // [rsp+C8h] [rbp+77h]
  int v46; // [rsp+D0h] [rbp+7Fh]

  v45 = a3;
  Block = a2;
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
  v41 = 0;
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
    v11 = lpCriticalSectiona;
    v12 = v46;
    goto LABEL_6;
  }
LABEL_17:
  EnterCriticalSection(v9);
  v15 = lpCriticalSectiona + 1;
  v16 = lpCriticalSectiona + 1;
  v40 = lpCriticalSectiona + 1;
  v42[0] = lpCriticalSectiona + 1;
  if ( lpCriticalSectiona[1].DebugInfo )
  {
    v17 = 0;
    v18 = *(unsigned __int8 **)(*((_QWORD *)v5 + 10) + 64LL);
    for ( i = *v18; *v18; i = *v18 )
    {
      ++v18;
      v17 = i + 101 * v17;
    }
    while ( 1 )
    {
      if ( !v16 || (DebugInfo = v16->DebugInfo) == 0 )
      {
LABEL_21:
        v4 = v45;
        v15 = v40;
        v3 = v36;
        break;
      }
      p_CriticalSection = &DebugInfo->CriticalSection;
      v23 = *(_QWORD *)(*((_QWORD *)v5 + 10) + 64LL);
      EnterCriticalSection((LPCRITICAL_SECTION)&DebugInfo[4].EntryCount);
      if ( v23
        && (v24 = p_CriticalSection[11]) != 0
        && (LockSemaphore = (unsigned __int8 *)v24[1].LockSemaphore) != 0
        && v17 == *((_DWORD *)p_CriticalSection + 64) )
      {
        v26 = v23 - (_QWORD)LockSemaphore;
        do
        {
          v27 = LockSemaphore[v26];
          v28 = *LockSemaphore - v27;
          if ( v28 )
            break;
          ++LockSemaphore;
        }
        while ( v27 );
        LeaveCriticalSection((LPCRITICAL_SECTION)(p_CriticalSection + 27));
        if ( !v28 )
        {
          if ( !v36 )
          {
            v5 = (struct _SSDP_REQUEST *)Block;
            updated = CSsdpCacheEntry::HrUpdateEntry(
                        (CSsdpCacheEntry *)p_CriticalSection,
                        (const struct _SSDP_REQUEST *)Block,
                        &v39,
                        &v37,
                        &v38);
            v12 = v37;
            appended = updated;
            if ( !updated && v37 )
              appended = CSsdpCacheEntry::HrAppendNetworkInfoToRequest((CSsdpCacheEntry *)p_CriticalSection, v5);
            v11 = lpCriticalSectiona;
            goto LABEL_6;
          }
          CUList<CSsdpCacheEntry>::Iterator::HrMoveToList(v42, &v41);
          --lpCriticalSectiona[1].LockCount;
          if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              67,
              WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids,
              (unsigned int)lpCriticalSectiona[1].LockCount);
          v11 = lpCriticalSectiona;
          v5 = (struct _SSDP_REQUEST *)Block;
LABEL_23:
          v12 = v46;
          goto LABEL_6;
        }
      }
      else
      {
        LeaveCriticalSection((LPCRITICAL_SECTION)(p_CriticalSection + 27));
      }
      v16 = (LPCRITICAL_SECTION)v16->DebugInfo;
      v5 = (struct _SSDP_REQUEST *)Block;
      if ( v16 )
      {
        v20 = v16->DebugInfo == 0;
        v42[0] = v16;
        if ( !v20 )
          continue;
      }
      goto LABEL_21;
    }
  }
  v20 = v3 == 0;
  v11 = lpCriticalSectiona;
  if ( !v20 || !v4 )
    goto LABEL_23;
  if ( !(unsigned int)CSsdpCacheEntryManager::IsCacheListNotFull(lpCriticalSectiona) )
  {
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids);
    goto LABEL_23;
  }
  Block = 0;
  v30 = CUList<CSsdpCacheEntry>::HrPushFrontDefault(&Block);
  v31 = (void **)Block;
  appended = v30;
  if ( v30 < 0
    || (appended = CSsdpCacheEntry::HrInitialize((CSsdpCacheEntry *)((char *)Block + 8), v5), appended < 0)
    || (appended = CSsdpCacheEntry::HrAppendNetworkInfoToRequest((CSsdpCacheEntry *)(v31 + 1), v5), appended < 0) )
  {
    v12 = v46;
  }
  else
  {
    v12 = 1;
    v38 = 1;
    appended = CSsdpCacheEntry::HrStartTimer((CSsdpCacheEntry *)(v31 + 1), v5);
    if ( appended >= 0 )
    {
      if ( v31 )
      {
        do
        {
          p_Block = v31;
          v31 = (void **)*v31;
        }
        while ( v31 );
      }
      else
      {
        p_Block = &Block;
      }
      v31 = 0;
      *p_Block = v15->DebugInfo;
      v33 = lpCriticalSectiona;
      v15->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)Block;
      ++v33[1].LockCount;
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          68,
          WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids,
          (unsigned int)lpCriticalSectiona[1].LockCount);
      v11 = lpCriticalSectiona;
    }
  }
  if ( v31 )
  {
    CUList<CSsdpCacheEntry>::Node::~Node(v31);
    free(v31);
  }
LABEL_6:
  LeaveCriticalSection(v11);
  if ( v12 )
    CSsdpNotifyRequestManager::HrCheckListNotifyForAliveOrByebye(&CSsdpNotifyRequestManager::s_instance, v5, v39, v38);
  Block = &v41;
  if ( v41 )
  {
    lpCriticalSectiona = 0;
    do
    {
      if ( (unsigned int)CUList<CRundownHelperBase *>::Iterator::HrGetItem(&Block, &lpCriticalSectiona) )
        break;
      v34 = (CSsdpCacheEntry *)lpCriticalSectiona;
      v35 = CSsdpCacheEntry::NotifyByeByeForAllAddressFamily((CSsdpCacheEntry *)lpCriticalSectiona);
      if ( v35 < 0 && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          70,
          WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids,
          (unsigned int)v35);
      appended = CSsdpCacheEntry::HrShutdown(v34, 0);
    }
    while ( !(unsigned int)CUList<__int64>::Iterator::HrNext(&Block) );
  }
  if ( appended && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      71,
      WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids,
      (unsigned int)appended);
  v13 = v41;
  if ( v41 )
  {
    CUList<CSsdpCacheEntry>::Node::~Node(v41);
    free(v13);
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180005260  mov     rax, rsp
0x180005263  mov     [rax+18h], r8d
0x180005267  mov     [rax+10h], rdx
0x18000526b  mov     [rax+8], rcx
0x18000526f  push    rbp
0x180005270  push    rbx
0x180005271  push    r13
0x180005273  lea     rbp, [rax-5Fh]
0x180005277  sub     rsp, 90h
0x18000527e  mov     [rax-20h], rsi
0x180005282  xor     esi, esi
0x180005284  mov     [rax-28h], rdi
0x180005288  mov     edi, r8d
0x18000528b  mov     [rax-30h], r12
0x18000528f  mov     r12, rdx
0x180005292  mov     [rax-38h], r14
0x180005296  mov     rax, rcx
0x180005299  mov     [rbp+57h+var_70], esi
0x18000529c  mov     [rbp+57h+var_68], esi
0x18000529f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800052a6  lea     r14, WPP_GLOBAL_Control
0x1800052ad  cmp     rcx, r14
0x1800052b0  jnz     loc_18000537C
0x1800052b6  mov     rbx, [r12+50h]
0x1800052bb  xor     ecx, ecx
0x1800052bd  mov     [rbp+57h+arg_18], ecx
0x1800052c0  mov     [rbp+57h+var_6C], ecx
0x1800052c3  mov     [rbp+57h+var_64], ecx
0x1800052c6  mov     [rbp+57h+var_58], rcx
0x1800052ca  mov     rcx, [rbx+10h]; Str1
0x1800052ce  test    rcx, rcx
0x1800052d1  jnz     loc_1800053AC
0x1800052d7  mov     rcx, rax; lpCriticalSection
0x1800052da  cmp     [rbx+48h], rsi
0x1800052de  jz      short loc_1800052F0
0x1800052e0  xor     r13d, r13d
0x1800052e3  cmp     [rbx+88h], rsi
0x1800052ea  jnz     loc_1800053CF
0x1800052f0  mov     r13d, 1
0x1800052f6  call    cs:__imp_EnterCriticalSection
0x1800052fd  nop     dword ptr [rax+rax+00h]
0x180005302  mov     rsi, [rbp+57h+lpCriticalSection]
0x180005306  lea     rdi, WPP_GLOBAL_Control
0x18000530d  mov     r14d, [rbp+57h+arg_18]
0x180005311  mov     rcx, rsi; lpCriticalSection
0x180005314  call    cs:__imp_LeaveCriticalSection
0x18000531b  nop     dword ptr [rax+rax+00h]
0x180005320  mov     rsi, [rsp+88h]
0x180005328  test    r14d, r14d
0x18000532b  mov     r14, [rsp+0A0h+var_30]
0x180005330  jnz     loc_180005560
0x180005336  cmp     [rbp+57h+var_58], 0
0x18000533b  lea     rax, [rbp+57h+var_58]
0x18000533f  mov     r12, [rsp+0A0h+var_28]
0x180005344  mov     [rbp+57h+Block], rax
0x180005348  jnz     loc_18000573B
0x18000534e  test    r13d, r13d
0x180005351  jnz     loc_1800057B1
0x180005357  mov     rbx, [rbp+57h+var_58]
0x18000535b  mov     rdi, [rsp+0A0h+var_20]
0x180005363  test    rbx, rbx
0x180005366  jnz     loc_1800057E8
0x18000536c  mov     eax, r13d
0x18000536f  add     rsp, 90h
0x180005376  pop     r13
0x180005378  pop     rbx
0x180005379  pop     rbp
0x18000537a  retn
0x18000537c  test    byte ptr [rcx+1Ch], 8
0x180005380  jz      loc_1800052B6
0x180005386  mov     rcx, [rcx+10h]
0x18000538a  mov     edx, 42h ; 'B'
0x18000538f  mov     [rsp+20h], r8d
0x180005394  mov     r9, rax
0x180005397  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x18000539e  call    WPP_SF_qd
0x1800053a3  mov     rax, [rbp+57h+lpCriticalSection]
0x1800053a7  jmp     loc_1800052B6
0x1800053ac  lea     rdx, aSsdpByebye; "ssdp:byebye"
0x1800053b3  call    strcmp_0
0x1800053b8  test    eax, eax
0x1800053ba  jnz     loc_1800054CF
0x1800053c0  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x1800053c4  mov     esi, 1
0x1800053c9  mov     [rbp+57h+var_70], esi
0x1800053cc  xor     r13d, r13d
0x1800053cf  call    cs:__imp_EnterCriticalSection
0x1800053d6  nop     dword ptr [rax+rax+00h]
0x1800053db  mov     [rsp+0A0h+var_38], r15
0x1800053e0  mov     r15, [rbp+57h+lpCriticalSection]
0x1800053e4  add     r15, 28h ; '('
0x1800053e8  mov     rbx, r15
0x1800053eb  mov     [rbp+57h+var_60], r15
0x1800053ef  mov     [rbp+57h+var_50], rbx
0x1800053f3  cmp     qword ptr [r15], 0
0x1800053f7  jz      short loc_180005439
0x1800053f9  mov     rax, [r12+50h]
0x1800053fe  xor     edi, edi
0x180005400  mov     rcx, [rax+40h]
0x180005404  movzx   eax, byte ptr [rcx]
0x180005407  test    al, al
0x180005409  jz      short loc_180005423
0x18000540b  nop     dword ptr [rax+rax+00h]
0x180005410  imul    edi, 65h ; 'e'
0x180005413  lea     rcx, [rcx+1]
0x180005417  movzx   eax, al
0x18000541a  add     edi, eax
0x18000541c  movzx   eax, byte ptr [rcx]
0x18000541f  test    al, al
0x180005421  jnz     short loc_180005410
0x180005423  test    rbx, rbx
0x180005426  jnz     short loc_18000545A
0x180005428  mov     edi, [rbp+57h+arg_10]
0x18000542b  lea     r14, WPP_GLOBAL_Control
0x180005432  mov     r15, [rbp+57h+var_60]
0x180005436  mov     esi, [rbp+57h+var_70]
0x180005439  test    esi, esi
0x18000543b  mov     rsi, [rbp+57h+lpCriticalSection]
0x18000543f  jz      loc_18000557C
0x180005445  lea     rdi, WPP_GLOBAL_Control
0x18000544c  mov     r14d, [rbp+57h+arg_18]
0x180005450  mov     r15, [rsp+0A0h+var_38]
0x180005455  jmp     loc_180005311
0x18000545a  mov     rax, [rbx]
0x18000545d  test    rax, rax
0x180005460  jz      short loc_180005428
0x180005462  lea     r15, [rax+8]
0x180005466  mov     rax, [r12+50h]
0x18000546b  lea     rcx, [r15+0D8h]; lpCriticalSection
0x180005472  mov     r14, [rax+40h]
0x180005476  call    cs:__imp_EnterCriticalSection
0x18000547d  nop     dword ptr [rax+rax+00h]
0x180005482  test    r14, r14
0x180005485  jz      short loc_180005499
0x180005487  mov     rax, [r15+58h]
0x18000548b  test    rax, rax
0x18000548e  jz      short loc_180005499
0x180005490  mov     rax, [rax+40h]
0x180005494  test    rax, rax
0x180005497  jnz     short loc_1800054D8
0x180005499  lea     rcx, [r15+0D8h]; lpCriticalSection
0x1800054a0  call    cs:__imp_LeaveCriticalSection
0x1800054a7  nop     dword ptr [rax+rax+00h]
0x1800054ac  mov     rbx, [rbx]
0x1800054af  mov     r12, [rbp+57h+Block]
0x1800054b3  test    rbx, rbx
0x1800054b6  jz      loc_180005428
0x1800054bc  cmp     qword ptr [rbx], 0
0x1800054c0  mov     [rbp+57h+var_50], rbx
0x1800054c4  jnz     loc_180005423
0x1800054ca  jmp     loc_180005428
0x1800054cf  mov     rax, [rbp+57h+lpCriticalSection]
0x1800054d3  jmp     loc_1800052D7
0x1800054d8  cmp     edi, [r15+100h]
0x1800054df  jnz     short loc_180005499
0x1800054e1  sub     r14, rax
0x1800054e4  movzx   esi, byte ptr [rax]
0x1800054e7  movzx   edx, byte ptr [rax+r14]
0x1800054ec  sub     esi, edx
0x1800054ee  jnz     short loc_1800054F7
0x1800054f0  inc     rax
0x1800054f3  test    edx, edx
0x1800054f5  jnz     short loc_1800054E4
0x1800054f7  lea     rcx, [r15+0D8h]; lpCriticalSection
0x1800054fe  call    cs:__imp_LeaveCriticalSection
0x180005505  nop     dword ptr [rax+rax+00h]
0x18000550a  test    esi, esi
0x18000550c  jnz     short loc_1800054AC
0x18000550e  cmp     [rbp+57h+var_70], esi
0x180005511  jnz     loc_180005614
0x180005517  mov     r12, [rbp+57h+Block]
0x18000551b  lea     rax, [rbp+57h+var_68]
0x18000551f  mov     rdx, r12; struct _SSDP_REQUEST *
0x180005522  mov     [rsp+20h], rax; unsigned int *
0x180005527  lea     r9, [rbp+57h+var_6C]; int *
0x18000552b  mov     rcx, r15; this
0x18000552e  lea     r8, [rbp+57h+var_64]; int *
0x180005532  call    ?HrUpdateEntry@CSsdpCacheEntry@@QEAAJPEBU_SSDP_REQUEST@@PEAH1PEAK@Z; CSsdpCacheEntry::HrUpdateEntry(_SSDP_REQUEST const *,int *,int *,ulong *)
0x180005537  mov     r14d, [rbp+57h+var_6C]
0x18000553b  mov     r13d, eax
0x18000553e  test    eax, eax
0x180005540  jnz     short loc_18000554B
0x180005542  test    r14d, r14d
0x180005545  jnz     loc_18000566B
0x18000554b  mov     rsi, [rbp+57h+lpCriticalSection]
0x18000554f  lea     rdi, WPP_GLOBAL_Control
0x180005556  mov     r15, [rsp+0A0h+var_38]
0x18000555b  jmp     loc_180005311
0x180005560  mov     r9d, [rbp+57h+var_68]; unsigned int
0x180005564  lea     rcx, ?s_instance@CSsdpNotifyRequestManager@@0V1@A; lpCriticalSection
0x18000556b  mov     r8d, [rbp+57h+var_64]; int
0x18000556f  mov     rdx, r12; struct _SSDP_REQUEST *
0x180005572  call    ?HrCheckListNotifyForAliveOrByebye@CSsdpNotifyRequestManager@@QEAAJPEBU_SSDP_REQUEST@@HK@Z; CSsdpNotifyRequestManager::HrCheckListNotifyForAliveOrByebye(_SSDP_REQUEST const *,int,ulong)
0x180005577  jmp     loc_180005336
0x18000557c  test    edi, edi
0x18000557e  jz      loc_180005445
0x180005584  mov     rcx, rsi; lpCriticalSection
0x180005587  call    ?IsCacheListNotFull@CSsdpCacheEntryManager@@QEAAHXZ; CSsdpCacheEntryManager::IsCacheListNotFull(void)
0x18000558c  test    eax, eax
0x18000558e  jz      short loc_1800055E0
0x180005590  lea     rcx, [rbp+57h+Block]
0x180005594  mov     [rbp+57h+Block], 0
0x18000559c  call    ?HrPushFrontDefault@?$CUList@VCSsdpCacheEntry@@@@QEAAJXZ; CUList<CSsdpCacheEntry>::HrPushFrontDefault(void)
0x1800055a1  mov     rbx, [rbp+57h+Block]
0x1800055a5  mov     r13d, eax
0x1800055a8  test    eax, eax
0x1800055aa  jns     loc_18000567E
0x1800055b0  mov     r14d, [rbp+57h+arg_18]
0x1800055b4  lea     rdi, WPP_GLOBAL_Control
0x1800055bb  test    rbx, rbx
0x1800055be  jz      loc_180005450
0x1800055c4  mov     rcx, rbx
0x1800055c7  call    ??1Node@?$CUList@VCSsdpCacheEntry@@@@QEAA@XZ; CUList<CSsdpCacheEntry>::Node::~Node(void)
0x1800055cc  mov     rcx, rbx; Block
0x1800055cf  call    cs:__imp_free
0x1800055d6  nop     dword ptr [rax+rax+00h]
0x1800055db  jmp     loc_180005450
0x1800055e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800055e7  cmp     rcx, r14
0x1800055ea  jz      loc_180005445
0x1800055f0  test    byte ptr [rcx+1Ch], 8
0x1800055f4  jz      loc_180005445
0x1800055fa  mov     rcx, [rcx+10h]
0x1800055fe  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180005605  mov     edx, 45h ; 'E'
0x18000560a  call    WPP_SF_
0x18000560f  jmp     loc_180005445
0x180005614  lea     rdx, [rbp+57h+var_58]
0x180005618  lea     rcx, [rbp+57h+var_50]
0x18000561c  call    ?HrMoveToList@Iterator@?$CUList@VCSsdpCacheEntry@@@@QEAAJAEAV2@@Z; CUList<CSsdpCacheEntry>::Iterator::HrMoveToList(CUList<CSsdpCacheEntry> &)
0x180005621  mov     rcx, [rbp+57h+lpCriticalSection]
0x180005625  dec     dword ptr [rcx+30h]
0x180005628  mov     rcx, cs:WPP_GLOBAL_Control
0x18000562f  lea     rdi, WPP_GLOBAL_Control
0x180005636  cmp     rcx, rdi
0x180005639  jz      short loc_18000565E
0x18000563b  test    byte ptr [rcx+1Ch], 8
0x18000563f  jz      short loc_18000565E
0x180005641  mov     rax, [rbp+57h+lpCriticalSection]
0x180005645  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x18000564c  mov     rcx, [rcx+10h]
0x180005650  mov     edx, 43h ; 'C'
0x180005655  mov     r9d, [rax+30h]
0x180005659  call    WPP_SF_d
0x18000565e  mov     rsi, [rbp+57h+lpCriticalSection]
0x180005662  mov     r12, [rbp+57h+Block]
0x180005666  jmp     loc_18000544C
0x18000566b  mov     rdx, r12; struct _SSDP_REQUEST *
0x18000566e  mov     rcx, r15; this
0x180005671  call    ?HrAppendNetworkInfoToRequest@CSsdpCacheEntry@@QEAAJPEAU_SSDP_REQUEST@@@Z; CSsdpCacheEntry::HrAppendNetworkInfoToRequest(_SSDP_REQUEST *)
0x180005676  mov     r13d, eax
0x180005679  jmp     loc_18000554B
0x18000567e  mov     rdx, r12; struct _SSDP_REQUEST *
0x180005681  lea     rcx, [rbx+8]; this
0x180005685  call    ?HrInitialize@CSsdpCacheEntry@@QEAAJPEBU_SSDP_REQUEST@@@Z; CSsdpCacheEntry::HrInitialize(_SSDP_REQUEST const *)
0x18000568a  mov     r13d, eax
0x18000568d  test    eax, eax
0x18000568f  js      loc_1800055B0
0x180005695  mov     rdx, r12; struct _SSDP_REQUEST *
0x180005698  lea     rcx, [rbx+8]; this
0x18000569c  call    ?HrAppendNetworkInfoToRequest@CSsdpCacheEntry@@QEAAJPEAU_SSDP_REQUEST@@@Z; CSsdpCacheEntry::HrAppendNetworkInfoToRequest(_SSDP_REQUEST *)
0x1800056a1  mov     r13d, eax
0x1800056a4  test    eax, eax
0x1800056a6  js      loc_1800055B0
0x1800056ac  mov     r14d, 1
0x1800056b2  lea     rcx, [rbx+8]; this
0x1800056b6  mov     rdx, r12; struct _SSDP_REQUEST *
0x1800056b9  mov     [rbp+57h+var_68], r14d
0x1800056bd  call    ?HrStartTimer@CSsdpCacheEntry@@QEAAJPEBU_SSDP_REQUEST@@@Z; CSsdpCacheEntry::HrStartTimer(_SSDP_REQUEST const *)
0x1800056c2  mov     r13d, eax
0x1800056c5  test    eax, eax
0x1800056c7  js      loc_1800055B4
0x1800056cd  test    rbx, rbx
0x1800056d0  jnz     short loc_1800056D8
0x1800056d2  lea     rcx, [rbp+57h+Block]
0x1800056d6  jmp     short loc_1800056E6
0x1800056d8  mov     rax, [rbx]
0x1800056db  mov     rcx, rbx
0x1800056de  mov     rbx, rax
0x1800056e1  test    rax, rax
0x1800056e4  jnz     short loc_1800056D8
0x1800056e6  mov     rax, [r15]
0x1800056e9  xor     ebx, ebx
0x1800056eb  mov     [rcx], rax
0x1800056ee  mov     rcx, [rbp+57h+lpCriticalSection]
0x1800056f2  mov     rax, [rbp+57h+Block]
0x1800056f6  mov     [r15], rax
0x1800056f9  inc     dword ptr [rcx+30h]
0x1800056fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180005703  lea     rdi, WPP_GLOBAL_Control
0x18000570a  cmp     rcx, rdi
0x18000570d  jz      short loc_180005732
0x18000570f  test    byte ptr [rcx+1Ch], 8
0x180005713  jz      short loc_180005732
0x180005715  mov     rax, [rbp+57h+lpCriticalSection]
0x180005719  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180005720  mov     rcx, [rcx+10h]
0x180005724  mov     edx, 44h ; 'D'
0x180005729  mov     r9d, [rax+30h]
0x18000572d  call    WPP_SF_d
  ... truncated ...
```
