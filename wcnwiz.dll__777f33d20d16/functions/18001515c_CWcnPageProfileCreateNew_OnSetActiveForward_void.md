# CWcnPageProfileCreateNew::OnSetActiveForward(void)

- ea: `0x18001515c`
- end: `0x1800153e0`
- name: `?OnSetActiveForward@CWcnPageProfileCreateNew@@QEAA_NXZ`
- size: `644`
- prototype: `bool __fastcall(CWcnPageProfileCreateNew *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180009be4`

## callees

- `0x180001820`
- `0x18000d630`
- `0x18000e19c`
- `0x1800105f0`
- `0x180013cdc`
- `0x180013e28`
- `0x180013e74`
- `0x1800143fc`
- `0x18001515c`
- `0x180015498`
- `0x18002de1c`

## import_xrefs

- `USER32!SendMessageW` at `0x1800151e7`
- `USER32!SendMessageW` at `0x1800152ae`
- `USER32!SendMessageW` at `0x1800152c9`
- `USER32!SendMessageW` at `0x1800152ef`
- `USER32!SendMessageW` at `0x1800151e7`
- `USER32!SendMessageW` at `0x1800152ae`
- `USER32!SendMessageW` at `0x1800152c9`
- `USER32!SendMessageW` at `0x1800152ef`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall CWcnPageProfileCreateNew::OnSetActiveForward(CWcnPageProfileCreateNew *this)
{
  int v2; // r15d
  const char *Indent; // rax
  __int64 v4; // r10
  unsigned int i; // esi
  __int64 v6; // r12
  int v7; // r13d
  unsigned int v8; // r14d
  unsigned int *v9; // rbx
  __int64 v10; // rax
  unsigned int v11; // r9d
  CWcnPageProfileCreateNew *v12; // rcx
  char v13; // r8
  __int64 v14; // rax
  int DecoratedString; // eax
  _BYTE *v16; // r10
  const char *v17; // rax
  __int64 v18; // r10
  unsigned int v20; // [rsp+30h] [rbp-D0h]
  unsigned int v21; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int *v23; // [rsp+40h] [rbp-C0h]
  unsigned int *v24; // [rsp+48h] [rbp-B8h]
  unsigned __int16 lParam[128]; // [rsp+50h] [rbp-B0h] BYREF

  v2 = 0;
  std::vector<CWcnNetworkProfile *>::vector<CWcnNetworkProfile *>(&v22);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v4 + 16), 21, WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids, Indent);
  }
  *((_BYTE *)this + 216) = 0;
  SendMessageW(*((HWND *)this + 41), 0x14Bu, 0, 0);
  *((_DWORD *)this + 53) = *(_DWORD *)(*((_QWORD *)this + 24) + 128LL);
  for ( i = 0; ; ++i )
  {
    if ( i >= 3 )
    {
      CWcnPageProfileCreateNew::PopulateCipherTypesList(this);
      goto LABEL_22;
    }
    v6 = 28LL * i;
    v7 = *(_DWORD *)&byte_1800369E0[v6];
    v8 = *(_DWORD *)&byte_1800369E0[v6 + 16];
    v21 = v8;
    v20 = *(_DWORD *)&byte_1800369E0[v6 + 4];
    v9 = v23;
    v10 = std::_Find_vectorized<unsigned int,unsigned int>(v22, v23, v8);
    v12 = (CWcnPageProfileCreateNew *)byte_1800369E0;
    if ( v9 == (unsigned int *)v10 )
    {
      v13 = byte_1800369E0[v6 + 8];
      if ( v13 == 1 )
        break;
      v14 = *((_QWORD *)this + 24);
      if ( (v7 & *(_DWORD *)(v14 + 124)) != 0 )
      {
        v12 = (CWcnPageProfileCreateNew *)v20;
        if ( (v20 & *(_DWORD *)(v14 + 128)) != 0 )
          break;
      }
    }
LABEL_17:
    ;
  }
  DecoratedString = CWcnPageProfileCreateNew::LoadDecoratedString(v12, v8, v13, v11, lParam);
  if ( DecoratedString >= 0 )
  {
    SendMessageW(*((HWND *)this + 41), 0x143u, 0, (LPARAM)lParam);
    SendMessageW(*((HWND *)this + 41), 0x151u, v2, i);
    if ( !v2 || v8 == *((_DWORD *)this + 50) )
      SendMessageW(*((HWND *)this + 41), 0x14Eu, v2, 0);
    ++v2;
    if ( v23 == v24 )
      std::vector<unsigned int>::_Emplace_reallocate<unsigned int const &>(&v22, v23, &v21);
    else
      *v23++ = v8;
    goto LABEL_17;
  }
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_26;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids,
      (unsigned int)DecoratedString);
LABEL_22:
    v16 = WPP_GLOBAL_Control;
  }
  if ( v16 != (_BYTE *)&WPP_GLOBAL_Control && v16[25] >= 6u )
  {
    v17 = GetIndent(-1);
    WPP_SF_s(*(_QWORD *)(v18 + 16), 23, WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids, v17);
  }
LABEL_26:
  if ( v22 )
    std::_Deallocate<16>(v22, ((unsigned __int64)v24 - v22) & 0xFFFFFFFFFFFFFFFCuLL);
  return 1;
}

```

## disassembly

```asm
0x18001515c  push    rbp
0x18001515e  push    rbx
0x18001515f  push    rsi
0x180015160  push    rdi
0x180015161  push    r12
0x180015163  push    r13
0x180015165  push    r14
0x180015167  push    r15
0x180015169  lea     rbp, [rsp-68h]
0x18001516e  sub     rsp, 168h
0x180015175  mov     rax, cs:__security_cookie
0x18001517c  xor     rax, rsp
0x18001517f  mov     [rbp+0A0h+var_50], rax
0x180015183  mov     rdi, rcx
0x180015186  xor     r15d, r15d
0x180015189  lea     rcx, [rsp+1A0h+var_168]
0x18001518e  call    ??0?$vector@PEAVCWcnNetworkProfile@@V?$allocator@PEAVCWcnNetworkProfile@@@std@@@std@@QEAA@XZ; std::vector<CWcnNetworkProfile *>::vector<CWcnNetworkProfile *>(void)
0x180015193  nop
0x180015194  lea     rax, WPP_GLOBAL_Control
0x18001519b  mov     r10, cs:WPP_GLOBAL_Control
0x1800151a2  cmp     r10, rax
0x1800151a5  jz      short loc_1800151CE
0x1800151a7  cmp     byte ptr [r10+19h], 6
0x1800151ac  jb      short loc_1800151CE
0x1800151ae  lea     ecx, [r15+1]; int
0x1800151b2  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800151b7  lea     edx, [r15+15h]
0x1800151bb  mov     r9, rax
0x1800151be  lea     r8, WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids
0x1800151c5  mov     rcx, [r10+10h]
0x1800151c9  call    WPP_SF_s
0x1800151ce  mov     byte ptr [rdi+0D8h], 0
0x1800151d5  xor     r9d, r9d; lParam
0x1800151d8  xor     r8d, r8d; wParam
0x1800151db  mov     edx, 14Bh; Msg
0x1800151e0  mov     rcx, [rdi+148h]; hWnd
0x1800151e7  call    cs:__imp_SendMessageW
0x1800151ed  mov     rax, [rdi+0C0h]
0x1800151f4  mov     ecx, [rax+80h]
0x1800151fa  mov     [rdi+0D4h], ecx
0x180015200  xor     esi, esi
0x180015202  lea     rcx, byte_1800369E0
0x180015209  cmp     esi, 3
0x18001520c  jnb     loc_180015360
0x180015212  mov     eax, esi
0x180015214  imul    r12, rax, 1Ch
0x180015218  mov     r13d, [r12+rcx]
0x18001521c  mov     r14d, [r12+rcx+10h]
0x180015221  mov     dword ptr [rsp+1A0h+var_170+4], r14d
0x180015226  mov     eax, [r12+rcx+4]
0x18001522b  mov     dword ptr [rsp+1A0h+var_170], eax
0x18001522f  mov     rbx, [rsp+1A0h+var_160]
0x180015234  mov     r8d, r14d
0x180015237  mov     rdx, rbx
0x18001523a  mov     rcx, [rsp+1A0h+var_168]
0x18001523f  call    ??$_Find_vectorized@II@std@@YAPEAIQEAI0I@Z; std::_Find_vectorized<uint,uint>(uint * const,uint * const,uint)
0x180015244  lea     rcx, byte_1800369E0
0x18001524b  cmp     rbx, rax
0x18001524e  jnz     loc_180015325
0x180015254  mov     r8b, [r12+rcx+8]; bool
0x180015259  cmp     r8b, 1
0x18001525d  jz      short loc_180015280
0x18001525f  mov     rax, [rdi+0C0h]
0x180015266  test    [rax+7Ch], r13d
0x18001526a  jz      loc_180015325
0x180015270  mov     ecx, dword ptr [rsp+1A0h+var_170]; this
0x180015274  test    [rax+80h], ecx
0x18001527a  jz      loc_18001531E
0x180015280  lea     rax, [rsp+1A0h+lParam]
0x180015285  mov     [rsp+1A0h+var_180], rax; unsigned __int16 *
0x18001528a  mov     edx, r14d; int
0x18001528d  call    ?LoadDecoratedString@CWcnPageProfileCreateNew@@AEAAJH_NKPEAG@Z; CWcnPageProfileCreateNew::LoadDecoratedString(int,bool,ulong,ushort *)
0x180015292  test    eax, eax
0x180015294  js      loc_18001532C
0x18001529a  lea     r9, [rsp+1A0h+lParam]; lParam
0x18001529f  xor     r8d, r8d; wParam
0x1800152a2  mov     edx, 143h; Msg
0x1800152a7  mov     rcx, [rdi+148h]; hWnd
0x1800152ae  call    cs:__imp_SendMessageW
0x1800152b4  movsxd  rbx, r15d
0x1800152b7  mov     r9d, esi; lParam
0x1800152ba  mov     r8, rbx; wParam
0x1800152bd  mov     edx, 151h; Msg
0x1800152c2  mov     rcx, [rdi+148h]; hWnd
0x1800152c9  call    cs:__imp_SendMessageW
0x1800152cf  test    r15d, r15d
0x1800152d2  jz      short loc_1800152DD
0x1800152d4  cmp     r14d, [rdi+0C8h]
0x1800152db  jnz     short loc_1800152F5
0x1800152dd  xor     r9d, r9d; lParam
0x1800152e0  mov     r8, rbx; wParam
0x1800152e3  mov     edx, 14Eh; Msg
0x1800152e8  mov     rcx, [rdi+148h]; hWnd
0x1800152ef  call    cs:__imp_SendMessageW
0x1800152f5  inc     r15d
0x1800152f8  mov     rdx, [rsp+1A0h+var_160]
0x1800152fd  cmp     rdx, [rsp+1A0h+var_158]
0x180015302  jz      short loc_18001530F
0x180015304  mov     [rdx], r14d
0x180015307  add     [rsp+1A0h+var_160], 4
0x18001530d  jmp     short loc_18001531E
0x18001530f  lea     r8, [rsp+1A0h+var_170+4]
0x180015314  lea     rcx, [rsp+1A0h+var_168]
0x180015319  call    ??$_Emplace_reallocate@AEBI@?$vector@IV?$allocator@I@std@@@std@@AEAAPEAIQEAIAEBI@Z; std::vector<uint>::_Emplace_reallocate<uint const &>(uint * const,uint const &)
0x18001531e  lea     rcx, byte_1800369E0
0x180015325  inc     esi
0x180015327  jmp     loc_180015209
0x18001532c  mov     r10, cs:WPP_GLOBAL_Control
0x180015333  lea     rbx, WPP_GLOBAL_Control
0x18001533a  cmp     r10, rbx
0x18001533d  jz      short loc_1800153A3
0x18001533f  cmp     byte ptr [r10+19h], 2
0x180015344  jb      short loc_180015376
0x180015346  mov     edx, 16h
0x18001534b  mov     r9d, eax
0x18001534e  lea     r8, WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids
0x180015355  mov     rcx, [r10+10h]
0x180015359  call    WPP_SF_d
0x18001535e  jmp     short loc_18001536F
0x180015360  mov     rcx, rdi; this
0x180015363  call    ?PopulateCipherTypesList@CWcnPageProfileCreateNew@@AEAAXXZ; CWcnPageProfileCreateNew::PopulateCipherTypesList(void)
0x180015368  lea     rbx, WPP_GLOBAL_Control
0x18001536f  mov     r10, cs:WPP_GLOBAL_Control
0x180015376  cmp     r10, rbx
0x180015379  jz      short loc_1800153A3
0x18001537b  cmp     byte ptr [r10+19h], 6
0x180015380  jb      short loc_1800153A3
0x180015382  or      ecx, 0FFFFFFFFh; int
0x180015385  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001538a  mov     edx, 17h
0x18001538f  mov     r9, rax
0x180015392  lea     r8, WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids
0x180015399  mov     rcx, [r10+10h]
0x18001539d  call    WPP_SF_s
0x1800153a2  nop
0x1800153a3  mov     rcx, [rsp+1A0h+var_168]
0x1800153a8  test    rcx, rcx
0x1800153ab  jz      short loc_1800153BE
0x1800153ad  mov     rdx, [rsp+1A0h+var_158]
0x1800153b2  sub     rdx, rcx
0x1800153b5  and     rdx, 0FFFFFFFFFFFFFFFCh
0x1800153b9  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800153be  mov     al, 1
0x1800153c0  mov     rcx, [rbp+0A0h+var_50]
0x1800153c4  xor     rcx, rsp; StackCookie
0x1800153c7  call    __security_check_cookie
0x1800153cc  add     rsp, 168h
0x1800153d3  pop     r15
0x1800153d5  pop     r14
0x1800153d7  pop     r13
0x1800153d9  pop     r12
0x1800153db  pop     rdi
0x1800153dc  pop     rsi
0x1800153dd  pop     rbx
0x1800153de  pop     rbp
0x1800153df  retn
```
