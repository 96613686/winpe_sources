# JournalReader::HandleWaitTimer(void)

- ea: `0x18000eb64`
- end: `0x18000edcf`
- name: `?HandleWaitTimer@JournalReader@@QEAAJXZ`
- size: `619`
- prototype: `__int64 __fastcall(JournalReader *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180012360`

## callees

- `0x180002cb0`
- `0x1800068e4`
- `0x18000cf80`
- `0x18000eb64`
- `0x18000ff58`
- `0x180010570`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x18000ebc6`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x18000ebc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ebee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ebee`

## pseudocode

```c
__int64 __fastcall JournalReader::HandleWaitTimer(JournalReader *this)
{
  int v2; // esi
  __int64 v3; // r8
  _QWORD *v4; // rcx
  DWORD LastError; // eax
  _QWORD *v6; // rax
  _QWORD *v7; // rbx
  _QWORD *v8; // r9
  _QWORD *v9; // rdx
  _QWORD *v10; // r8
  __int64 *v11; // rax
  __int64 v12; // rdx
  _QWORD *v13; // rdx
  _QWORD *v14; // rdx
  char *v15; // r9
  int *v17; // [rsp+28h] [rbp-40h]
  char v18[32]; // [rsp+0h] [rbp-68h] BYREF
  int v19; // [rsp+78h] [rbp+10h] BYREF
  int v20; // [rsp+80h] [rbp+18h]
  __int64 v21; // [rsp+88h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_880a4eb608c037d792798d7e53d23858_Traceguids);
  }
  v19 = 0;
  v2 = 0;
  v20 = 0;
  *((_BYTE *)this + 80) = 0;
  if ( CancelWaitableTimer(*((HANDLE *)this + 9)) )
    goto LABEL_10;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_880a4eb608c037d792798d7e53d23858_Traceguids, LastError);
LABEL_10:
    v4 = WPP_GLOBAL_Control;
  }
  while ( 1 )
  {
    v6 = (_QWORD *)*((_QWORD *)this + 17);
    v7 = (_QWORD *)*v6;
    if ( (_QWORD *)*v6 == v6 )
      break;
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 4u )
    {
      v8 = v7 + 4;
      if ( v7[7] >= 8u )
        v8 = (_QWORD *)*v8;
      WPP_SF_SD(
        v4[2],
        38,
        (unsigned int)WPP_880a4eb608c037d792798d7e53d23858_Traceguids,
        (_DWORD)v8,
        *((_DWORD *)v7 + 16));
    }
    try
    {
      if ( (v7[8] & 0x200) != 0 )
      {
        if ( *(_QWORD *)this )
        {
          v9 = v7 + 4;
          if ( v7[7] >= 8u )
            v9 = (_QWORD *)*v9;
          (*(void (__fastcall **)(_QWORD, _QWORD *))(**(_QWORD **)this + 24LL))(*(_QWORD *)this, v9);
        }
      }
      else
      {
        if ( (v7[8] & 0x1000) != 0 && *(_QWORD *)this )
        {
          v10 = v7 + 4;
          if ( v7[7] >= 8u )
            v10 = (_QWORD *)*v10;
          v11 = (__int64 *)v7[9];
          if ( v11 )
            v12 = *v11;
          else
            v12 = 0;
          (*(void (__fastcall **)(_QWORD, __int64, _QWORD *))(**(_QWORD **)this + 16LL))(*(_QWORD *)this, v12, v10);
        }
        if ( (v7[8] & 0x800) != 0 && *(_QWORD *)this )
        {
          v13 = v7 + 4;
          if ( v7[7] >= 8u )
            v13 = (_QWORD *)*v13;
          (*(void (__fastcall **)(_QWORD, _QWORD *))(**(_QWORD **)this + 8LL))(*(_QWORD *)this, v13);
        }
        if ( (v7[8] & 1) != 0 && *(_QWORD *)this )
        {
          v14 = v7 + 4;
          if ( v7[7] >= 8u )
            v14 = (_QWORD *)*v14;
          (***(void (__fastcall ****)(_QWORD, _QWORD *))this)(*(_QWORD *)this, v14);
        }
      }
      std::_Tree<std::_Tmap_traits<std::wstring,JournalReader::ChangeData,JournalReader::wstringless,t_allocator<std::pair<std::wstring const,JournalReader::ChangeData>>,0>>::erase(
        (__int64 **)this + 17,
        &v21,
        v7);
      v2 = 1;
      v20 = 1;
      v4 = WPP_GLOBAL_Control;
    }
    catch ( ... )
    {
      tsched::KnownExceptionToHResult((tsched *)v4, v18, v3, v15, (unsigned __int8)&v19, v17);
    }
  }
  if ( !v2 && v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 4u )
    WPP_SF_(v4[2], 39, WPP_880a4eb608c037d792798d7e53d23858_Traceguids);
  if ( *((_DWORD *)this + 32) )
    JournalReader::_ReadUsnJournal(this, 1, v3);
  return 0;
}

```

## disassembly

```asm
0x18000eb64  mov     [rsp+arg_0], rcx
0x18000eb69  push    rbx
0x18000eb6a  push    rsi
0x18000eb6b  push    rdi
0x18000eb6c  push    r12
0x18000eb6e  push    r14
0x18000eb70  push    r15
0x18000eb72  sub     rsp, 38h
0x18000eb76  mov     rdi, rcx
0x18000eb79  lea     r14, WPP_GLOBAL_Control
0x18000eb80  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb87  cmp     rcx, r14
0x18000eb8a  jz      short loc_18000EBAD
0x18000eb8c  test    byte ptr [rcx+1Ch], 2
0x18000eb90  jz      short loc_18000EBAD
0x18000eb92  cmp     byte ptr [rcx+19h], 4
0x18000eb96  jb      short loc_18000EBAD
0x18000eb98  mov     edx, 24h ; '$'
0x18000eb9d  lea     r8, WPP_880a4eb608c037d792798d7e53d23858_Traceguids
0x18000eba4  mov     rcx, [rcx+10h]
0x18000eba8  call    WPP_SF_
0x18000ebad  xor     r15d, r15d
0x18000ebb0  mov     [rsp+68h+arg_8], r15d
0x18000ebb5  xor     esi, esi
0x18000ebb7  mov     [rsp+68h+arg_10], esi
0x18000ebbe  mov     [rdi+50h], sil
0x18000ebc2  mov     rcx, [rdi+48h]; hTimer
0x18000ebc6  call    cs:__imp_CancelWaitableTimer
0x18000ebcd  nop     dword ptr [rax+rax+00h]
0x18000ebd2  test    eax, eax
0x18000ebd4  jnz     short loc_18000EC17
0x18000ebd6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ebdd  cmp     rcx, r14
0x18000ebe0  jz      short loc_18000EC1E
0x18000ebe2  test    byte ptr [rcx+1Ch], 2
0x18000ebe6  jz      short loc_18000EC1E
0x18000ebe8  cmp     byte ptr [rcx+19h], 2
0x18000ebec  jb      short loc_18000EC1E
0x18000ebee  call    cs:__imp_GetLastError
0x18000ebf5  nop     dword ptr [rax+rax+00h]
0x18000ebfa  lea     edx, [rsi+25h]
0x18000ebfd  mov     r9d, eax
0x18000ec00  lea     r8, WPP_880a4eb608c037d792798d7e53d23858_Traceguids
0x18000ec07  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec0e  mov     rcx, [rcx+10h]
0x18000ec12  call    WPP_SF_d
0x18000ec17  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec1e  lea     r12, [rdi+88h]
0x18000ec25  mov     rax, [r12]
0x18000ec29  mov     rbx, [rax]
0x18000ec2c  cmp     rbx, rax
0x18000ec2f  jnz     short loc_18000EC36
0x18000ec31  jmp     loc_18000ED7F
0x18000ec36  cmp     rcx, r14
0x18000ec39  jz      short loc_18000EC71
0x18000ec3b  test    byte ptr [rcx+1Ch], 2
0x18000ec3f  jz      short loc_18000EC71
0x18000ec41  cmp     byte ptr [rcx+19h], 4
0x18000ec45  jb      short loc_18000EC71
0x18000ec47  mov     eax, [rbx+40h]
0x18000ec4a  lea     r9, [rbx+20h]
0x18000ec4e  cmp     qword ptr [rbx+38h], 8
0x18000ec53  jb      short loc_18000EC58
0x18000ec55  mov     r9, [r9]
0x18000ec58  mov     edx, 26h ; '&'
0x18000ec5d  mov     [rsp+68h+var_48], eax
0x18000ec61  lea     r8, WPP_880a4eb608c037d792798d7e53d23858_Traceguids
0x18000ec68  mov     rcx, [rcx+10h]
0x18000ec6c  call    WPP_SF_SD
0x18000ec71  test    dword ptr [rbx+40h], 200h
0x18000ec78  jz      short loc_18000ECA5
0x18000ec7a  mov     rcx, [rdi]
0x18000ec7d  test    rcx, rcx
0x18000ec80  jz      loc_18000ED35
0x18000ec86  mov     rax, [rcx]
0x18000ec89  lea     rdx, [rbx+20h]
0x18000ec8d  cmp     qword ptr [rbx+38h], 8
0x18000ec92  jb      short loc_18000EC97
0x18000ec94  mov     rdx, [rdx]
0x18000ec97  mov     rax, [rax+18h]
0x18000ec9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eca0  jmp     loc_18000ED35
0x18000eca5  test    dword ptr [rbx+40h], 1000h
0x18000ecac  jz      short loc_18000ECE3
0x18000ecae  mov     rcx, [rdi]
0x18000ecb1  test    rcx, rcx
0x18000ecb4  jz      short loc_18000ECE3
0x18000ecb6  mov     rax, [rcx]
0x18000ecb9  mov     r9, [rax+10h]
0x18000ecbd  lea     r8, [rbx+20h]
0x18000ecc1  cmp     qword ptr [rbx+38h], 8
0x18000ecc6  jb      short loc_18000ECCB
0x18000ecc8  mov     r8, [r8]
0x18000eccb  mov     rax, [rbx+48h]
0x18000eccf  test    rax, rax
0x18000ecd2  jz      short loc_18000ECD9
0x18000ecd4  mov     rdx, [rax]
0x18000ecd7  jmp     short loc_18000ECDB
0x18000ecd9  xor     edx, edx
0x18000ecdb  mov     rax, r9
0x18000ecde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ece3  test    dword ptr [rbx+40h], 800h
0x18000ecea  jz      short loc_18000ED0E
0x18000ecec  mov     rcx, [rdi]
0x18000ecef  test    rcx, rcx
0x18000ecf2  jz      short loc_18000ED0E
0x18000ecf4  mov     rax, [rcx]
0x18000ecf7  lea     rdx, [rbx+20h]
0x18000ecfb  cmp     qword ptr [rbx+38h], 8
0x18000ed00  jb      short loc_18000ED05
0x18000ed02  mov     rdx, [rdx]
0x18000ed05  mov     rax, [rax+8]
0x18000ed09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed0e  test    byte ptr [rbx+40h], 1
0x18000ed12  jz      short loc_18000ED35
0x18000ed14  mov     rcx, [rdi]
0x18000ed17  test    rcx, rcx
0x18000ed1a  jz      short loc_18000ED35
0x18000ed1c  mov     rax, [rcx]
0x18000ed1f  lea     rdx, [rbx+20h]
0x18000ed23  cmp     qword ptr [rbx+38h], 8
0x18000ed28  jb      short loc_18000ED2D
0x18000ed2a  mov     rdx, [rdx]
0x18000ed2d  mov     rax, [rax]
0x18000ed30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed35  mov     r8, rbx
0x18000ed38  lea     rdx, [rsp+68h+arg_18]
0x18000ed40  mov     rcx, r12
0x18000ed43  call    ?erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UChangeData@JournalReader@@Uwstringless@4@V?$t_allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UChangeData@JournalReader@@@std@@@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UChangeData@JournalReader@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UChangeData@JournalReader@@@std@@@std@@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,JournalReader::ChangeData,JournalReader::wstringless,t_allocator<std::pair<std::wstring const,JournalReader::ChangeData>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,JournalReader::ChangeData>>>>)
0x18000ed48  mov     esi, 1
0x18000ed4d  mov     [rsp+68h+arg_10], esi
0x18000ed54  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed5b  jmp     loc_18000EC1E
0x18000ed60  lea     r14, WPP_GLOBAL_Control
0x18000ed67  mov     rdi, [rsp+68h+arg_0]
0x18000ed6c  mov     r15d, [rsp+68h+arg_8]
0x18000ed71  mov     esi, [rsp+68h+arg_10]
0x18000ed78  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed7f  test    esi, esi
0x18000ed81  jnz     short loc_18000EDA7
0x18000ed83  cmp     rcx, r14
0x18000ed86  jz      short loc_18000EDA7
0x18000ed88  test    byte ptr [rcx+1Ch], 2
0x18000ed8c  jz      short loc_18000EDA7
0x18000ed8e  cmp     byte ptr [rcx+19h], 4
0x18000ed92  jb      short loc_18000EDA7
0x18000ed94  lea     edx, [rsi+27h]
0x18000ed97  lea     r8, WPP_880a4eb608c037d792798d7e53d23858_Traceguids
0x18000ed9e  mov     rcx, [rcx+10h]
0x18000eda2  call    WPP_SF_
0x18000eda7  cmp     dword ptr [rdi+80h], 0
0x18000edae  jz      short loc_18000EDBD
0x18000edb0  mov     edx, 1; int
0x18000edb5  mov     rcx, rdi; this
0x18000edb8  call    ?_ReadUsnJournal@JournalReader@@AEAAJH@Z; JournalReader::_ReadUsnJournal(int)
0x18000edbd  mov     eax, r15d
0x18000edc0  add     rsp, 38h
0x18000edc4  pop     r15
0x18000edc6  pop     r14
0x18000edc8  pop     r12
0x18000edca  pop     rdi
0x18000edcb  pop     rsi
0x18000edcc  pop     rbx
0x18000edcd  retn
```
