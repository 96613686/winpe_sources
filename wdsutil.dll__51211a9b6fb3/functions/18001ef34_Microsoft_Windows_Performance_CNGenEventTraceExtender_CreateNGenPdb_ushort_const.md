# Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(ushort const *)

- ea: `0x18001ef34`
- end: `0x18001f27c`
- name: `?CreateNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEBG@Z`
- size: `840`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CNGenEventTraceExtender *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001f970`

## callees

- `0x18000a89c`
- `0x18000e390`
- `0x1800182e4`
- `0x18001ef34`
- `0x18001f284`
- `0x180020808`
- `0x18003085c`
- `0x1800319f0`
- `0x180034010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18001f18e`
- `msvcrt!wcsrchr` at `0x18001f1a5`
- `msvcrt!wcsrchr` at `0x18001f18e`
- `msvcrt!wcsrchr` at `0x18001f1a5`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001efde`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001eff1`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001efde`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001eff1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(
        Microsoft::Windows::Performance::CNGenEventTraceExtender *this,
        XPerf::Internal *a2)
{
  wchar_t *v2; // rdi
  unsigned int v4; // r13d
  void **v5; // r12
  void **v6; // r15
  union _CVDD *v7; // rax
  int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // r8
  int v11; // ebx
  unsigned int v12; // esi
  __int64 v13; // rsi
  int v14; // esi
  bool v16; // bl
  unsigned int v17; // r9d
  struct _RSDS *v18; // r8
  _BYTE *v19; // rdx
  unsigned __int64 v20; // rcx
  wchar_t *v21; // rbx
  wchar_t *v22; // rax
  unsigned __int16 *v23; // rbx
  unsigned __int16 *v24; // rdx
  int v25; // [rsp+30h] [rbp-61h]
  int v26; // [rsp+30h] [rbp-61h]
  int v27; // [rsp+38h] [rbp-59h]
  int v28; // [rsp+38h] [rbp-59h]
  int v29; // [rsp+40h] [rbp-51h]
  int v30; // [rsp+40h] [rbp-51h]
  int v31; // [rsp+48h] [rbp-49h]
  int v32; // [rsp+48h] [rbp-49h]
  bool v33[8]; // [rsp+58h] [rbp-39h] BYREF
  unsigned int v34; // [rsp+60h] [rbp-31h] BYREF
  unsigned __int16 *v35; // [rsp+68h] [rbp-29h] BYREF
  struct _RSDS *v36; // [rsp+70h] [rbp-21h]
  __int64 v37; // [rsp+78h] [rbp-19h]
  struct _EVENT_DATA_DESCRIPTOR v38; // [rsp+80h] [rbp-11h] BYREF
  wchar_t *v39; // [rsp+90h] [rbp-1h]
  int v40; // [rsp+98h] [rbp+7h]
  int v41; // [rsp+9Ch] [rbp+Bh]
  unsigned int *v42; // [rsp+A0h] [rbp+Fh]
  __int64 v43; // [rsp+A8h] [rbp+17h]

  v37 = -2;
  v2 = (wchar_t *)a2;
  v4 = 0;
  v33[0] = 0;
  v34 = *((_DWORD *)this + 40);
  v5 = (void **)((char *)this + 168);
  if ( !*((_QWORD *)this + 21) )
    return 2147942414LL;
  v6 = (void **)((char *)this + 176);
  v7 = (union _CVDD *)*((_QWORD *)this + 22);
  if ( !v7 )
    return 2147942414LL;
  v8 = CvDbgInfoFromImage(a2, v7, v25, v27, v29, v31, (unsigned int)v33);
  v11 = v8;
  if ( v8 < 0 )
  {
    if ( v8 != -2146893023 )
    {
LABEL_8:
      if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
      {
        v34 = v11;
        if ( v2 )
        {
          v13 = -1;
          do
            ++v13;
          while ( v2[v13] );
          v14 = 2 * v13 + 2;
        }
        else
        {
          v14 = 10;
        }
        if ( !v2 )
          v2 = L"NULL";
        v39 = v2;
        v40 = v14;
        v41 = 0;
        v42 = &v34;
        v43 = 4;
        McGenEventWrite_EventWriteTransfer(v9, (const EVENT_DESCRIPTOR *)TraceMerge_NGEN_BinaryNotFound, v10, 3u, &v38);
      }
      return (unsigned int)v11;
    }
    *((_DWORD *)this + 40) = 0;
    operator delete[](*v5);
    *v5 = 0;
    operator delete[](*v6);
    *v6 = 0;
    v12 = v34;
    if ( (unsigned __int8)ATL::CAutoVectorPtr<_CVDD>::Allocate(v5, v34)
      && (unsigned __int8)ATL::CAutoVectorPtr<unsigned long>::Allocate(v6, v12) )
    {
      *((_DWORD *)this + 40) = v12;
      v11 = CvDbgInfoFromImage((XPerf::Internal *)v2, (union _CVDD *)*v6, v26, v28, v30, v32, (unsigned int)v33);
      if ( v11 < 0 )
        goto LABEL_8;
      goto LABEL_18;
    }
    return 2147942414LL;
  }
LABEL_18:
  if ( !v34 )
    return 0;
  v16 = v33[0];
  while ( 1 )
  {
    v17 = *((_DWORD *)*v6 + v4);
    if ( v17 > 0x18 )
    {
      v18 = (struct _RSDS *)((char *)*v5 + 1576 * v4);
      v36 = v18;
      if ( *(_DWORD *)v18 == 1396986706 )
      {
        v19 = (char *)v18 + 24;
        if ( v18 != (struct _RSDS *)-24LL )
        {
          v20 = v17 - 24;
          if ( v20 <= 0x7FFFFFFF )
          {
            do
            {
              if ( !*v19 )
                break;
              ++v19;
              --v20;
            }
            while ( v20 );
            if ( v20
              && (int)Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(
                        this,
                        *((char **)this + 8),
                        v2,
                        v18,
                        v16) < 0 )
            {
              break;
            }
          }
        }
      }
    }
LABEL_34:
    if ( ++v4 >= v34 )
      return 0;
  }
  v35 = (unsigned __int16 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  v21 = wcsrchr(v2, 0x2Fu);
  v22 = wcsrchr(v2, 0x5Cu);
  if ( v21 > v22 )
    v22 = v21;
  if ( v22 )
  {
    ATL::CSimpleStringT<unsigned short,0>::SetString((char **)&v35, v2, v22 - v2);
    v23 = v35;
    Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(this, (char *)v35, v2, v36, v33[0]);
    if ( _InterlockedDecrement((volatile signed __int32 *)v23 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v23 - 3) + 8LL))(*((_QWORD *)v23 - 3));
    v16 = v33[0];
    goto LABEL_34;
  }
  v24 = v35 - 12;
  if ( _InterlockedDecrement((volatile signed __int32 *)v35 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v24 + 8LL))(*(_QWORD *)v24);
  return 1;
}

```

## disassembly

```asm
0x18001ef34  mov     rax, rsp
0x18001ef37  push    rbp
0x18001ef38  push    rsi
0x18001ef39  push    rdi
0x18001ef3a  push    r12
0x18001ef3c  push    r13
0x18001ef3e  push    r14
0x18001ef40  push    r15
0x18001ef42  lea     rbp, [rax-5Fh]
0x18001ef46  sub     rsp, 0B0h
0x18001ef4d  mov     [rbp+57h+var_70], 0FFFFFFFFFFFFFFFEh
0x18001ef55  mov     [rax+18h], rbx
0x18001ef59  mov     rax, cs:__security_cookie
0x18001ef60  xor     rax, rsp
0x18001ef63  mov     [rbp+57h+var_38], rax
0x18001ef67  mov     rdi, rdx
0x18001ef6a  mov     r14, rcx
0x18001ef6d  xor     r13d, r13d
0x18001ef70  mov     [rbp+57h+var_90], r13b
0x18001ef74  mov     eax, [rcx+0A0h]
0x18001ef7a  mov     [rbp+57h+var_88], eax
0x18001ef7d  lea     r12, [rcx+0A8h]
0x18001ef84  mov     r9, [r12]
0x18001ef88  test    r9, r9
0x18001ef8b  jz      loc_18001F24F
0x18001ef91  lea     r15, [rcx+0B0h]
0x18001ef98  mov     rax, [r15]
0x18001ef9b  test    rax, rax
0x18001ef9e  jz      loc_18001F24F
0x18001efa4  lea     rcx, [rbp+57h+var_90]
0x18001efa8  mov     qword ptr [rsp+0E0h+var_A0+8], rcx; unsigned int
0x18001efad  mov     [rsp+20h], rax; union _CVDD *
0x18001efb2  lea     r8, [rbp+57h+var_88]
0x18001efb6  mov     rcx, rdx; this
0x18001efb9  call    CvDbgInfoFromImage
0x18001efbe  mov     ebx, eax
0x18001efc0  test    eax, eax
0x18001efc2  jns     loc_18001F0CD
0x18001efc8  cmp     eax, 80090321h
0x18001efcd  jnz     loc_18001F055
0x18001efd3  mov     [r14+0A0h], r13d
0x18001efda  mov     rcx, [r12]
0x18001efde  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001efe5  nop     dword ptr [rax+rax+00h]
0x18001efea  mov     [r12], r13
0x18001efee  mov     rcx, [r15]
0x18001eff1  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001eff8  nop     dword ptr [rax+rax+00h]
0x18001effd  mov     [r15], r13
0x18001f000  mov     esi, [rbp+57h+var_88]
0x18001f003  mov     edx, esi
0x18001f005  mov     rcx, r12
0x18001f008  call    ?Allocate@?$CAutoVectorPtr@T_CVDD@@@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<_CVDD>::Allocate(unsigned __int64)
0x18001f00d  test    al, al
0x18001f00f  jz      loc_18001F24F
0x18001f015  mov     edx, esi
0x18001f017  mov     rcx, r15
0x18001f01a  call    ?Allocate@?$CAutoVectorPtr@K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<ulong>::Allocate(unsigned __int64)
0x18001f01f  test    al, al
0x18001f021  jz      loc_18001F24F
0x18001f027  mov     [r14+0A0h], esi
0x18001f02e  lea     rax, [rbp+57h+var_90]
0x18001f032  mov     qword ptr [rsp+0E0h+var_A0+8], rax; unsigned int
0x18001f037  mov     rax, [r15]
0x18001f03a  mov     [rsp+20h], rax; union _CVDD *
0x18001f03f  mov     r9, [r12]
0x18001f043  lea     r8, [rbp+57h+var_88]
0x18001f047  mov     rcx, rdi; this
0x18001f04a  call    CvDbgInfoFromImage
0x18001f04f  mov     ebx, eax
0x18001f051  test    eax, eax
0x18001f053  jns     short loc_18001F0CD
0x18001f055  test    cs:Microsoft_Windows_XPerfCoreEnableBits, 1
0x18001f05c  jz      short loc_18001F0C6
0x18001f05e  mov     [rbp+57h+var_88], ebx
0x18001f061  test    rdi, rdi
0x18001f064  jz      short loc_18001F07D
0x18001f066  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001f06a  inc     rsi
0x18001f06d  cmp     [rdi+rsi*2], r13w
0x18001f072  jnz     short loc_18001F06A
0x18001f074  lea     esi, ds:2[rsi*2]
0x18001f07b  jmp     short loc_18001F082
0x18001f07d  mov     esi, 0Ah
0x18001f082  lea     rax, aNull; "NULL"
0x18001f089  test    rdi, rdi
0x18001f08c  cmovz   rdi, rax
0x18001f090  mov     [rbp+57h+var_58], rdi
0x18001f094  mov     [rbp+57h+var_50], esi
0x18001f097  mov     [rbp+57h+var_4C], r13d
0x18001f09b  lea     rax, [rbp+57h+var_88]
0x18001f09f  mov     [rbp+57h+var_48], rax
0x18001f0a3  mov     [rbp+57h+var_40], 4
0x18001f0ab  lea     rax, [rbp+57h+var_68]
0x18001f0af  mov     [rsp+20h], rax
0x18001f0b4  mov     r9d, 3
0x18001f0ba  lea     rdx, TraceMerge_NGEN_BinaryNotFound
0x18001f0c1  call    McGenEventWrite_EventWriteTransfer
0x18001f0c6  mov     eax, ebx
0x18001f0c8  jmp     loc_18001F254
0x18001f0cd  cmp     [rbp+57h+var_88], r13d
0x18001f0d1  jbe     loc_18001F220
0x18001f0d7  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001f0db  mov     bl, [rbp+57h+var_90]
0x18001f0de  mov     ecx, r13d
0x18001f0e1  mov     rax, [r15]
0x18001f0e4  mov     r9d, [rax+rcx*4]
0x18001f0e8  cmp     r9d, 18h
0x18001f0ec  jbe     loc_18001F213
0x18001f0f2  imul    r8, rcx, 628h
0x18001f0f9  add     r8, [r12]
0x18001f0fd  mov     [rbp+57h+var_78], r8
0x18001f101  cmp     dword ptr [r8], 53445352h
0x18001f108  jnz     loc_18001F213
0x18001f10e  lea     rdx, [r8+18h]
0x18001f112  test    rdx, rdx
0x18001f115  jz      loc_18001F213
0x18001f11b  lea     eax, [r9-18h]
0x18001f11f  mov     ecx, eax
0x18001f121  cmp     rcx, 7FFFFFFFh
0x18001f128  ja      loc_18001F213
0x18001f12e  test    eax, eax
0x18001f130  jz      short loc_18001F140
0x18001f132  cmp     byte ptr [rdx], 0
0x18001f135  jz      short loc_18001F140
0x18001f137  inc     rdx
0x18001f13a  sub     rcx, 1
0x18001f13e  jnz     short loc_18001F132
0x18001f140  test    rcx, rcx
0x18001f143  jz      loc_18001F213
0x18001f149  mov     [rsp+20h], bl; bool
0x18001f14d  mov     r9, r8; struct _RSDS *
0x18001f150  mov     r8, rdi; unsigned __int16 *
0x18001f153  mov     rdx, [r14+40h]; unsigned __int16 *
0x18001f157  mov     rcx, r14; this
0x18001f15a  call    ?CreateNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBG0AEBU_RSDS@@_N@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(ushort const *,ushort const *,_RSDS const &,bool)
0x18001f15f  test    eax, eax
0x18001f161  jns     loc_18001F213
0x18001f167  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001f16e  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001f175  mov     rax, [rax+18h]
0x18001f179  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f17e  add     rax, 18h
0x18001f182  mov     [rbp+57h+var_80], rax
0x18001f186  mov     edx, 2Fh ; '/'; Ch
0x18001f18b  mov     rcx, rdi; Str
0x18001f18e  call    cs:__imp_wcsrchr
0x18001f195  nop     dword ptr [rax+rax+00h]
0x18001f19a  mov     rbx, rax
0x18001f19d  mov     edx, 5Ch ; '\'; Ch
0x18001f1a2  mov     rcx, rdi; Str
0x18001f1a5  call    cs:__imp_wcsrchr
0x18001f1ac  nop     dword ptr [rax+rax+00h]
0x18001f1b1  cmp     rbx, rax
0x18001f1b4  cmova   rax, rbx
0x18001f1b8  test    rax, rax
0x18001f1bb  jz      short loc_18001F224
0x18001f1bd  sub     rax, rdi
0x18001f1c0  sar     rax, 1
0x18001f1c3  mov     r8d, eax
0x18001f1c6  mov     rdx, rdi
0x18001f1c9  lea     rcx, [rbp+57h+var_80]
0x18001f1cd  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18001f1d2  mov     al, [rbp+57h+var_90]
0x18001f1d5  mov     [rsp+20h], al; bool
0x18001f1d9  mov     r9, [rbp+57h+var_78]; struct _RSDS *
0x18001f1dd  mov     r8, rdi; unsigned __int16 *
0x18001f1e0  mov     rbx, [rbp+57h+var_80]
0x18001f1e4  mov     rdx, rbx; unsigned __int16 *
0x18001f1e7  mov     rcx, r14; this
0x18001f1ea  call    ?CreateNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBG0AEBU_RSDS@@_N@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(ushort const *,ushort const *,_RSDS const &,bool)
0x18001f1ef  nop
0x18001f1f0  lea     rdx, [rbx-18h]
0x18001f1f4  mov     eax, esi
0x18001f1f6  lock xadd [rdx+10h], eax
0x18001f1fb  add     eax, esi
0x18001f1fd  test    eax, eax
0x18001f1ff  jg      short loc_18001F210
0x18001f201  mov     rcx, [rdx]
0x18001f204  mov     rax, [rcx]
0x18001f207  mov     rax, [rax+8]
0x18001f20b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f210  mov     bl, [rbp+57h+var_90]
0x18001f213  inc     r13d
0x18001f216  cmp     r13d, [rbp+57h+var_88]
0x18001f21a  jb      loc_18001F0DE
0x18001f220  xor     eax, eax
0x18001f222  jmp     short loc_18001F254
0x18001f224  mov     rdx, [rbp+57h+var_80]
0x18001f228  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18001f22c  mov     ecx, esi
0x18001f22e  lock xadd [rdx+10h], ecx
0x18001f233  add     ecx, esi
0x18001f235  test    ecx, ecx
0x18001f237  jg      short loc_18001F248
0x18001f239  mov     rcx, [rdx]
0x18001f23c  mov     r8, [rcx]
0x18001f23f  mov     rax, [r8+8]
0x18001f243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f248  mov     eax, 1
0x18001f24d  jmp     short loc_18001F254
0x18001f24f  mov     eax, 8007000Eh
0x18001f254  mov     rcx, [rbp+57h+var_38]
0x18001f258  xor     rcx, rsp; StackCookie
0x18001f25b  call    __security_check_cookie
0x18001f260  mov     rbx, [rsp+0E0h+arg_10]
0x18001f268  add     rsp, 0B0h
0x18001f26f  pop     r15
0x18001f271  pop     r14
0x18001f273  pop     r13
0x18001f275  pop     r12
0x18001f277  pop     rdi
0x18001f278  pop     rsi
0x18001f279  pop     rbp
0x18001f27a  retn
```
