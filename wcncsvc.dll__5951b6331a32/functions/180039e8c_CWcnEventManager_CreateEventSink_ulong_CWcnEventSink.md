# CWcnEventManager::CreateEventSink(ulong *,CWcnEventSink * *)

- ea: `0x180039e8c`
- end: `0x18003a0c0`
- name: `?CreateEventSink@CWcnEventManager@@QEAAJPEAKPEAPEAVCWcnEventSink@@@Z`
- size: `564`
- prototype: `__int64 __fastcall(CWcnEventManager *__hidden this, unsigned int *, struct CWcnEventSink **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180037d20`

## callees

- `0x180001404`
- `0x1800015d0`
- `0x180004fb8`
- `0x180005014`
- `0x18000cd68`
- `0x18003986c`
- `0x180039e8c`
- `0x180053004`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180039fc4`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180039fc4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039f42`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039f42`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a05f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a05f`

## pseudocode

```c
__int64 __fastcall CWcnEventManager::CreateEventSink(
        CWcnEventManager *this,
        unsigned int *a2,
        struct CWcnEventSink **a3)
{
  __int64 v4; // r14
  _QWORD *v5; // r10
  const char *Indent; // rax
  __int64 v7; // r10
  int v9; // esi
  struct _RTL_CRITICAL_SECTION *v10; // r13
  _QWORD *v11; // rax
  __int64 v12; // rcx
  _QWORD *v13; // rdi
  char *v14; // rax
  __int64 v15; // rcx
  struct CWcnEventSink *v16; // rdi
  _QWORD *v17; // rdi
  __int64 v18; // rdx
  __int64 v19; // rax
  unsigned int v20; // ecx
  CWcnEventSink *v21; // rax
  unsigned int v22; // eax
  __int64 v23; // r10
  CWcnEventSink *v24; // rdi
  __int64 v25; // rax
  std::bad_alloc *v26; // [rsp+30h] [rbp-48h] BYREF
  __int64 v27; // [rsp+80h] [rbp+8h]

  v4 = qword_180075810;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v7 + 16), 10, WPP_e0de45765f7234980260fe5ced58e1dd_Traceguids, Indent);
    v5 = WPP_GLOBAL_Control;
  }
  if ( !a3 )
  {
    if ( v5 != &WPP_GLOBAL_Control && *((_BYTE *)v5 + 25) >= 2u )
      WPP_SF_s(v5[2], 11, WPP_e0de45765f7234980260fe5ced58e1dd_Traceguids, "ppEventSink");
    return 2147500035LL;
  }
  v9 = 0;
  *a3 = 0;
  v10 = (struct _RTL_CRITICAL_SECTION *)(v4 + 48);
  EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 48));
  if ( *(_BYTE *)(v4 + 88) )
  {
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      if ( !*(_QWORD *)(v4 + 32) )
      {
        v11 = operator new(0x10u);
        v13 = v11;
        if ( v11 )
        {
          *v11 = 0;
          v11[1] = 0;
          *v11 = std::_List_alloc<0,std::_List_base_types<CWcnPeer *>>::_Buynode0(v12, 0, 0);
        }
        else
        {
          v13 = 0;
        }
        *(_QWORD *)(v4 + 32) = v13;
      }
      v14 = (char *)operator new(0x70u);
      v16 = (struct CWcnEventSink *)v14;
      if ( v14 )
      {
        *((_DWORD *)v14 + 4) = 0;
        *((_QWORD *)v14 + 8) = 0;
        *((_QWORD *)v14 + 9) = 0;
        *((_QWORD *)v14 + 10) = 0;
        *((_QWORD *)v14 + 11) = 0;
        v14[100] = 0;
        *((_DWORD *)v14 + 26) = 0;
        InitializeCriticalSection((LPCRITICAL_SECTION)(v14 + 24));
      }
      else
      {
        v16 = 0;
      }
      *a3 = v16;
      v17 = *(_QWORD **)(v4 + 32);
      v27 = *v17;
      v18 = std::_List_buy<CWcnPeer *>::_Buynode<CWcnPeer * const &>(v15, *v17, *(_QWORD *)(*v17 + 8LL), a3);
      v19 = v17[1];
      if ( v19 == 0xAAAAAAAAAAAAAA9LL )
        std::_Xlength_error("list<T> too long");
      v17[1] = v19 + 1;
      *(_QWORD *)(v27 + 8) = v18;
      **(_QWORD **)(v18 + 8) = v18;
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', &v26) )
      {
        if ( *a3 )
        {
          v24 = *a3;
          CWcnEventSink::~CWcnEventSink(*a3);
          operator delete(v24);
          *a3 = 0;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v25 = (*(__int64 (__fastcall **)(std::bad_alloc *))(*(_QWORD *)v26 + 8LL))(v26);
          WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_e0de45765f7234980260fe5ced58e1dd_Traceguids, v25);
        }
        v9 = -2147024882;
        v10 = (struct _RTL_CRITICAL_SECTION *)(v4 + 48);
        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18003A046);
        goto LABEL_22;
      }
    }
    v20 = ++*(_DWORD *)(v4 + 40);
    *a2 = v20;
    v21 = *a3;
    *((_QWORD *)v21 + 11) = v4;
    *((_DWORD *)v21 + 24) = v20;
  }
  else
  {
    v9 = -2147023641;
  }
LABEL_22:
  LeaveCriticalSection(v10);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (v9 < 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u) )
  {
    v22 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v23 + 16), 13, (unsigned int)WPP_e0de45765f7234980260fe5ced58e1dd_Traceguids, v22, v9);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180039e8c  mov     [rsp+arg_10], r8
0x180039e91  mov     [rsp+arg_8], rdx
0x180039e96  mov     [rsp+arg_0], rcx
0x180039e9b  push    rbx
0x180039e9c  push    rsi
0x180039e9d  push    rdi
0x180039e9e  push    r12
0x180039ea0  push    r13
0x180039ea2  push    r14
0x180039ea4  push    r15
0x180039ea6  sub     rsp, 40h
0x180039eaa  mov     r15, r8
0x180039ead  mov     r14, cs:qword_180075810
0x180039eb4  lea     r12, WPP_GLOBAL_Control
0x180039ebb  mov     r10, cs:WPP_GLOBAL_Control
0x180039ec2  cmp     r10, r12
0x180039ec5  jz      short loc_180039EF7
0x180039ec7  cmp     byte ptr [r10+19h], 6
0x180039ecc  jb      short loc_180039EF7
0x180039ece  mov     ecx, 1; int
0x180039ed3  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180039ed8  mov     edx, 0Ah
0x180039edd  mov     r9, rax
0x180039ee0  lea     r8, WPP_e0de45765f7234980260fe5ced58e1dd_Traceguids
0x180039ee7  mov     rcx, [r10+10h]
0x180039eeb  call    WPP_SF_s
0x180039ef0  mov     r10, cs:WPP_GLOBAL_Control
0x180039ef7  xor     ebx, ebx
0x180039ef9  test    r15, r15
0x180039efc  jnz     short loc_180039F2E
0x180039efe  cmp     r10, r12
0x180039f01  jz      short loc_180039F24
0x180039f03  cmp     byte ptr [r10+19h], 2
0x180039f08  jb      short loc_180039F24
0x180039f0a  lea     edx, [rbx+0Bh]
0x180039f0d  lea     r9, aPpeventsink; "ppEventSink"
0x180039f14  lea     r8, WPP_e0de45765f7234980260fe5ced58e1dd_Traceguids
0x180039f1b  mov     rcx, [r10+10h]
0x180039f1f  call    WPP_SF_s
0x180039f24  mov     eax, 80004003h
0x180039f29  jmp     loc_18003A0A2
0x180039f2e  mov     esi, ebx
0x180039f30  mov     [r15], rbx
0x180039f33  lea     r13, [r14+30h]
0x180039f37  mov     [rsp+78h+arg_18], r13
0x180039f3f  mov     rcx, r13; lpCriticalSection
0x180039f42  call    cs:__imp_EnterCriticalSection
0x180039f48  cmp     [r14+58h], bl
0x180039f4c  jnz     short loc_180039F58
0x180039f4e  mov     esi, 800704E7h
0x180039f53  jmp     loc_18003A05C
0x180039f58  cmp     [r14+20h], rbx
0x180039f5c  jnz     short loc_180039F95
0x180039f5e  mov     ecx, 10h; Size
0x180039f63  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180039f68  mov     rdi, rax
0x180039f6b  mov     [rsp+78h+arg_0], rax
0x180039f73  test    rax, rax
0x180039f76  jz      short loc_180039F8E
0x180039f78  mov     [rax], rbx
0x180039f7b  mov     [rax+8], rbx
0x180039f7f  xor     r8d, r8d
0x180039f82  xor     edx, edx
0x180039f84  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@PEAVCWcnPeer@@V?$allocator@PEAVCWcnPeer@@@std@@@std@@@std@@QEAAPEAU?$_List_node@PEAVCWcnPeer@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<CWcnPeer *>>::_Buynode0(std::_List_node<CWcnPeer *,void *> *,std::_List_node<CWcnPeer *,void *> *)
0x180039f89  mov     [rdi], rax
0x180039f8c  jmp     short loc_180039F91
0x180039f8e  mov     rdi, rbx
0x180039f91  mov     [r14+20h], rdi
0x180039f95  mov     ecx, 70h ; 'p'; Size
0x180039f9a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180039f9f  mov     rdi, rax
0x180039fa2  test    rax, rax
0x180039fa5  jz      short loc_180039FCC
0x180039fa7  mov     [rax+10h], ebx
0x180039faa  mov     [rax+40h], rbx
0x180039fae  mov     [rax+48h], rbx
0x180039fb2  mov     [rax+50h], rbx
0x180039fb6  mov     [rax+58h], rbx
0x180039fba  mov     [rax+64h], bl
0x180039fbd  mov     [rax+68h], ebx
0x180039fc0  lea     rcx, [rax+18h]; lpCriticalSection
0x180039fc4  call    cs:__imp_InitializeCriticalSection
0x180039fca  jmp     short loc_180039FCF
0x180039fcc  mov     rdi, rbx
0x180039fcf  mov     [r15], rdi
0x180039fd2  mov     rdi, [r14+20h]
0x180039fd6  mov     rax, [rdi]
0x180039fd9  mov     [rsp+78h+arg_0], rax
0x180039fe1  mov     r9, r15
0x180039fe4  mov     r8, [rax+8]
0x180039fe8  mov     rdx, rax
0x180039feb  call    ??$_Buynode@AEBQEAVCWcnPeer@@@?$_List_buy@PEAVCWcnPeer@@V?$allocator@PEAVCWcnPeer@@@std@@@std@@QEAAPEAU?$_List_node@PEAVCWcnPeer@@PEAX@1@PEAU21@0AEBQEAVCWcnPeer@@@Z; std::_List_buy<CWcnPeer *>::_Buynode<CWcnPeer * const &>(std::_List_node<CWcnPeer *,void *> *,std::_List_node<CWcnPeer *,void *> *,CWcnPeer * const &)
0x180039ff0  mov     rdx, rax
0x180039ff3  mov     rax, [rdi+8]
0x180039ff7  mov     rcx, 0AAAAAAAAAAAAAA9h
0x18003a001  sub     rcx, rax
0x18003a004  cmp     rcx, 1
0x18003a008  jb      loc_18003A0B2
0x18003a00e  inc     rax
0x18003a011  mov     [rdi+8], rax
0x18003a015  mov     rax, [rsp+78h+arg_0]
0x18003a01d  mov     [rax+8], rdx
0x18003a021  mov     rax, [rdx+8]
0x18003a025  mov     [rax], rdx
0x18003a028  inc     dword ptr [r14+28h]
0x18003a02c  mov     ecx, [r14+28h]
0x18003a030  mov     rax, [rsp+78h+arg_8]
0x18003a038  mov     [rax], ecx
0x18003a03a  mov     rax, [r15]
0x18003a03d  mov     [rax+58h], r14
0x18003a041  mov     [rax+60h], ecx
0x18003a044  jmp     short loc_18003A05C
0x18003a046  lea     r12, WPP_GLOBAL_Control
0x18003a04d  mov     esi, dword ptr [rsp+78h+arg_10]
0x18003a054  mov     r13, [rsp+78h+arg_18]
0x18003a05c  mov     rcx, r13; lpCriticalSection
0x18003a05f  call    cs:__imp_LeaveCriticalSection
0x18003a065  mov     r10, cs:WPP_GLOBAL_Control
0x18003a06c  cmp     r10, r12
0x18003a06f  jz      short loc_18003A0A0
0x18003a071  test    esi, esi
0x18003a073  js      short loc_18003A07C
0x18003a075  cmp     byte ptr [r10+19h], 6
0x18003a07a  jb      short loc_18003A0A0
0x18003a07c  or      ecx, 0FFFFFFFFh; int
0x18003a07f  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003a084  mov     edx, 0Dh
0x18003a089  mov     [rsp+78h+var_58], esi
0x18003a08d  mov     r9, rax
0x18003a090  lea     r8, WPP_e0de45765f7234980260fe5ced58e1dd_Traceguids
0x18003a097  mov     rcx, [r10+10h]
0x18003a09b  call    WPP_SF_sd
0x18003a0a0  mov     eax, esi
0x18003a0a2  add     rsp, 40h
0x18003a0a6  pop     r15
0x18003a0a8  pop     r14
0x18003a0aa  pop     r13
0x18003a0ac  pop     r12
0x18003a0ae  pop     rdi
0x18003a0af  pop     rsi
0x18003a0b0  pop     rbx
0x18003a0b1  retn
0x18003a0b2  lea     rcx, aListTTooLong; "list<T> too long"
0x18003a0b9  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
