# CWcnSession::AddVendorExtension(CWcnSession::tagWcnSessionExtensionDirection,tagWCNPRPC_VENDOR_EXTENSION_TYPE,CSbSafeBuffer const *)

- ea: `0x180014fa4`
- end: `0x180015278`
- name: `?AddVendorExtension@CWcnSession@@QEAAJW4tagWcnSessionExtensionDirection@1@W4tagWCNPRPC_VENDOR_EXTENSION_TYPE@@PEBVCSbSafeBuffer@@@Z`
- size: `724`
- prototype: `__int64 __fastcall(__int64, int, int, const struct CSbSafeBuffer *)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, loader_planting`

## callers

- `0x180029b60`
- `0x1800378e0`

## callees

- `0x180001404`
- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x18000a558`
- `0x18000a5ac`
- `0x18000a74c`
- `0x180014fa4`
- `0x1800196cc`
- `0x18001dbbc`
- `0x180053004`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001521b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001521b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015059`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015059`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015205`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015205`

## pseudocode

```c
__int64 __fastcall CWcnSession::AddVendorExtension(__int64 a1, int a2, int a3, const struct CSbSafeBuffer *a4)
{
  __int64 v5; // r13
  __int64 v6; // rbx
  CSbSafeBuffer *v8; // rdi
  _QWORD *v9; // r10
  const char *Indent; // rax
  __int64 v11; // r10
  struct _RTL_CRITICAL_SECTION *v13; // r15
  __int64 v14; // rbx
  _QWORD *v15; // rsi
  _QWORD *v16; // rax
  int v17; // ebx
  unsigned int v18; // eax
  __int64 v19; // r10
  CSbSafeBuffer *v20; // rax
  int v21; // eax
  int v22; // eax
  unsigned int v23; // eax
  __int64 v24; // r10
  __int64 v25; // rax
  CSbSafeBuffer *v26; // [rsp+30h] [rbp-58h] BYREF
  struct _RTL_CRITICAL_SECTION *v27; // [rsp+38h] [rbp-50h]
  CSbSafeBuffer *v28; // [rsp+40h] [rbp-48h]
  std::bad_alloc *v29; // [rsp+48h] [rbp-40h] BYREF

  v5 = a3;
  v6 = a2;
  v8 = 0;
  v26 = 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v11 + 16), 98, WPP_a137d119f5dc35a130051116e3170526_Traceguids, Indent);
    v9 = WPP_GLOBAL_Control;
  }
  if ( !a4 )
  {
    if ( v9 != &WPP_GLOBAL_Control && *((_BYTE *)v9 + 25) >= 2u )
      WPP_SF_s(v9[2], 99, WPP_a137d119f5dc35a130051116e3170526_Traceguids, "pBuffer");
    return 2147500035LL;
  }
  v13 = (struct _RTL_CRITICAL_SECTION *)(a1 + 1536);
  v27 = (struct _RTL_CRITICAL_SECTION *)(a1 + 1536);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 1536));
  if ( (int)v6 >= 0 && (unsigned int)v5 <= 2 )
  {
    _mm_lfence();
    v14 = v5 + 3 * (v6 + 62);
    v15 = *(_QWORD **)(a1 + 8 * v14);
    if ( !v15 )
    {
      if ( __eh34_try(-1, 0) )
      {
        __eh34_scope_strut(0);
        v16 = operator new(0x18u);
        v15 = v16;
        if ( v16 )
        {
          *v16 = 0;
          v16[1] = 0;
          v16[2] = 0;
        }
        else
        {
          v15 = 0;
        }
        *(_QWORD *)(a1 + 8 * v14) = v15;
      }
      if ( __eh34_catch(0) )
      {
        if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', &v29) )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v25 = (*(__int64 (__fastcall **)(std::bad_alloc *))(*(_QWORD *)v29 + 8LL))(v29);
            WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 100, WPP_a137d119f5dc35a130051116e3170526_Traceguids, v25);
          }
          v17 = -2147024882;
          v8 = v26;
          v13 = v27;
          __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180015114);
          goto LABEL_35;
        }
      }
    }
    if ( (unsigned __int64)((__int64)(v15[1] - *v15) >> 3) < 0x19 )
    {
      v20 = (CSbSafeBuffer *)operator new(0x20u);
      v28 = v20;
      if ( v20 )
        v8 = CSbSafeBuffer::CSbSafeBuffer(v20);
      else
        v8 = 0;
      v26 = v8;
      v21 = CSbSafeBuffer::CopyFromBuffer(v8, a4);
      v17 = v21;
      if ( v21 >= 0 )
      {
        std::vector<CSmState *>::push_back(v15, &v26);
        v8 = 0;
        v26 = 0;
        if ( !(_DWORD)v5 && a2 == 1 )
        {
          v22 = CWcnPeer::SetDiscoveryVendorExtensions(*(_QWORD *)(a1 + 32), v15);
          v17 = v22;
          if ( v22 < 0
            && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              104,
              WPP_a137d119f5dc35a130051116e3170526_Traceguids,
              (unsigned int)v22);
          }
        }
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          102,
          WPP_a137d119f5dc35a130051116e3170526_Traceguids,
          (unsigned int)v21);
      }
    }
    else
    {
      v17 = -2147023604;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v18 = (unsigned int)GetIndent(0);
        WPP_SF_sd(*(_QWORD *)(v19 + 16), 101, (unsigned int)WPP_a137d119f5dc35a130051116e3170526_Traceguids, v18, 25);
      }
    }
    goto LABEL_35;
  }
  v17 = -2147024809;
LABEL_35:
  LeaveCriticalSection(v13);
  if ( v8 )
  {
    CSbSafeBuffer::~CSbSafeBuffer(v8);
    operator delete(v8);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (v17 < 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u) )
  {
    v23 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v24 + 16), 105, (unsigned int)WPP_a137d119f5dc35a130051116e3170526_Traceguids, v23, v17);
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180014fa4  mov     rax, rsp
0x180014fa7  mov     [rax+8], rbx
0x180014fab  mov     [rax+18h], rsi
0x180014faf  mov     [rax+20h], r9
0x180014fb3  mov     [rax+10h], edx
0x180014fb6  push    rdi
0x180014fb7  push    r12
0x180014fb9  push    r13
0x180014fbb  push    r14
0x180014fbd  push    r15
0x180014fbf  sub     rsp, 60h
0x180014fc3  mov     rsi, r9
0x180014fc6  movsxd  r13, r8d
0x180014fc9  movsxd  rbx, edx
0x180014fcc  mov     r12, rcx
0x180014fcf  xor     edi, edi
0x180014fd1  mov     [rax-58h], rdi
0x180014fd5  lea     r14, WPP_GLOBAL_Control
0x180014fdc  mov     r10, cs:WPP_GLOBAL_Control
0x180014fe3  cmp     r10, r14
0x180014fe6  jz      short loc_180015014
0x180014fe8  cmp     byte ptr [r10+19h], 6
0x180014fed  jb      short loc_180015014
0x180014fef  lea     ecx, [rdi+1]; int
0x180014ff2  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180014ff7  lea     edx, [rdi+62h]
0x180014ffa  mov     r9, rax
0x180014ffd  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x180015004  mov     rcx, [r10+10h]
0x180015008  call    WPP_SF_s
0x18001500d  mov     r10, cs:WPP_GLOBAL_Control
0x180015014  test    rsi, rsi
0x180015017  jnz     short loc_180015049
0x180015019  cmp     r10, r14
0x18001501c  jz      short loc_18001503F
0x18001501e  cmp     byte ptr [r10+19h], 2
0x180015023  jb      short loc_18001503F
0x180015025  lea     edx, [rsi+63h]
0x180015028  lea     r9, aPbuffer; "pBuffer"
0x18001502f  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x180015036  mov     rcx, [r10+10h]
0x18001503a  call    WPP_SF_s
0x18001503f  mov     eax, 80004003h
0x180015044  jmp     loc_18001525E
0x180015049  lea     r15, [r12+600h]
0x180015051  mov     [rsp+88h+var_50], r15
0x180015056  mov     rcx, r15; lpCriticalSection
0x180015059  call    cs:__imp_EnterCriticalSection
0x18001505f  test    ebx, ebx
0x180015061  js      loc_1800151FD
0x180015067  cmp     r13d, 2
0x18001506b  ja      loc_1800151FD
0x180015071  lfence
0x180015074  lea     rax, [rbx+3Eh]
0x180015078  lea     rbx, [rax+rax*2]
0x18001507c  add     rbx, r13
0x18001507f  mov     rsi, [r12+rbx*8]
0x180015083  test    rsi, rsi
0x180015086  jnz     short loc_1800150B7
0x180015088  lea     ecx, [rsi+18h]; Size
0x18001508b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015090  mov     rsi, rax
0x180015093  test    rax, rax
0x180015096  jz      short loc_1800150B1
0x180015098  mov     qword ptr [rax], 0
0x18001509f  mov     qword ptr [rax+8], 0
0x1800150a7  mov     qword ptr [rax+10h], 0
0x1800150af  jmp     short loc_1800150B3
0x1800150b1  xor     esi, esi
0x1800150b3  mov     [r12+rbx*8], rsi
0x1800150b7  mov     rax, [rsi+8]
0x1800150bb  sub     rax, [rsi]
0x1800150be  sar     rax, 3
0x1800150c2  cmp     rax, 19h
0x1800150c6  jb      short loc_180015131
0x1800150c8  mov     ebx, 8007050Ch
0x1800150cd  mov     r10, cs:WPP_GLOBAL_Control
0x1800150d4  cmp     r10, r14
0x1800150d7  jz      loc_180015202
0x1800150dd  cmp     byte ptr [r10+19h], 2
0x1800150e2  jb      loc_180015202
0x1800150e8  xor     ecx, ecx; int
0x1800150ea  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800150ef  mov     edx, 65h ; 'e'
0x1800150f4  mov     [rsp+88h+var_68], 19h
0x1800150fc  mov     r9, rax
0x1800150ff  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x180015106  mov     rcx, [r10+10h]
0x18001510a  call    WPP_SF_sd
0x18001510f  jmp     loc_180015202
0x180015114  lea     r14, WPP_GLOBAL_Control
0x18001511b  mov     ebx, dword ptr [rsp+88h+arg_18]
0x180015122  mov     rdi, [rsp+88h+var_58]
0x180015127  mov     r15, [rsp+88h+var_50]
0x18001512c  jmp     loc_180015202
0x180015131  mov     ecx, 20h ; ' '; Size
0x180015136  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001513b  mov     [rsp+88h+var_48], rax
0x180015140  test    rax, rax
0x180015143  jz      short loc_180015152
0x180015145  mov     rcx, rax; this
0x180015148  call    ??0CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::CSbSafeBuffer(void)
0x18001514d  mov     rdi, rax
0x180015150  jmp     short loc_180015154
0x180015152  xor     edi, edi
0x180015154  mov     [rsp+88h+var_58], rdi
0x180015159  mov     rdx, [rsp+88h+arg_18]; struct CSbSafeBuffer *
0x180015161  mov     rcx, rdi; this
0x180015164  call    ?CopyFromBuffer@CSbSafeBuffer@@QEAAJPEBV1@@Z; CSbSafeBuffer::CopyFromBuffer(CSbSafeBuffer const *)
0x180015169  mov     ebx, eax
0x18001516b  test    eax, eax
0x18001516d  jns     short loc_18001519C
0x18001516f  mov     rcx, cs:WPP_GLOBAL_Control
0x180015176  cmp     rcx, r14
0x180015179  jz      short loc_18001519A
0x18001517b  cmp     byte ptr [rcx+19h], 2
0x18001517f  jb      short loc_18001519A
0x180015181  mov     edx, 66h ; 'f'
0x180015186  mov     r9d, eax
0x180015189  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x180015190  mov     rcx, [rcx+10h]
0x180015194  call    WPP_SF_d
0x180015199  nop
0x18001519a  jmp     short loc_180015202
0x18001519c  lea     rdx, [rsp+88h+var_58]
0x1800151a1  mov     rcx, rsi
0x1800151a4  call    ?push_back@?$vector@PEAVCSmState@@V?$allocator@PEAVCSmState@@@std@@@std@@QEAAXAEBQEAVCSmState@@@Z; std::vector<CSmState *>::push_back(CSmState * const &)
0x1800151a9  xor     edi, edi
0x1800151ab  mov     [rsp+88h+var_58], rdi
0x1800151b0  test    r13d, r13d
0x1800151b3  jnz     short loc_180015202
0x1800151b5  cmp     [rsp+88h+arg_8], 1
0x1800151bd  jnz     short loc_180015202
0x1800151bf  mov     rdx, rsi
0x1800151c2  mov     rcx, [r12+20h]
0x1800151c7  call    ?SetDiscoveryVendorExtensions@CWcnPeer@@QEAAJPEBV?$vector@PEAVCSbSafeBuffer@@V?$allocator@PEAVCSbSafeBuffer@@@std@@@std@@@Z; CWcnPeer::SetDiscoveryVendorExtensions(std::vector<CSbSafeBuffer *> const *)
0x1800151cc  mov     ebx, eax
0x1800151ce  test    eax, eax
0x1800151d0  jns     short loc_180015202
0x1800151d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800151d9  cmp     rcx, r14
0x1800151dc  jz      short loc_180015202
0x1800151de  cmp     byte ptr [rcx+19h], 2
0x1800151e2  jb      short loc_180015202
0x1800151e4  lea     edx, [r13+68h]
0x1800151e8  mov     r9d, eax
0x1800151eb  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x1800151f2  mov     rcx, [rcx+10h]
0x1800151f6  call    WPP_SF_d
0x1800151fb  jmp     short loc_180015202
0x1800151fd  mov     ebx, 80070057h
0x180015202  mov     rcx, r15; lpCriticalSection
0x180015205  call    cs:__imp_LeaveCriticalSection
0x18001520b  test    rdi, rdi
0x18001520e  jz      short loc_180015221
0x180015210  mov     rcx, rdi; this
0x180015213  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x180015218  mov     rcx, rdi
0x18001521b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180015221  mov     r10, cs:WPP_GLOBAL_Control
0x180015228  cmp     r10, r14
0x18001522b  jz      short loc_18001525C
0x18001522d  test    ebx, ebx
0x18001522f  js      short loc_180015238
0x180015231  cmp     byte ptr [r10+19h], 6
0x180015236  jb      short loc_18001525C
0x180015238  or      ecx, 0FFFFFFFFh; int
0x18001523b  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180015240  mov     edx, 69h ; 'i'
0x180015245  mov     [rsp+88h+var_68], ebx
0x180015249  mov     r9, rax
0x18001524c  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x180015253  mov     rcx, [r10+10h]
0x180015257  call    WPP_SF_sd
0x18001525c  mov     eax, ebx
0x18001525e  lea     r11, [rsp+88h+var_28]
0x180015263  mov     rbx, [r11+30h]
0x180015267  mov     rsi, [r11+40h]
0x18001526b  mov     rsp, r11
0x18001526e  pop     r15
0x180015270  pop     r14
0x180015272  pop     r13
0x180015274  pop     r12
0x180015276  pop     rdi
0x180015277  retn
```
