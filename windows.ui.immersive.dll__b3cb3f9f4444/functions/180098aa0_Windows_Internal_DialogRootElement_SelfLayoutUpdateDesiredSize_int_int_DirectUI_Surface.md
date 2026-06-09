# Windows::Internal::DialogRootElement::_SelfLayoutUpdateDesiredSize(int,int,DirectUI::Surface *)

- ea: `0x180098aa0`
- end: `0x180098c81`
- name: `?_SelfLayoutUpdateDesiredSize@DialogRootElement@Internal@Windows@@EEAA?AUtagSIZE@@HHPEAVSurface@DirectUI@@@Z`
- size: `481`
- prototype: `struct tagSIZE __fastcall(Windows::Internal::DialogRootElement *__hidden this, int, int, struct DirectUI::Surface *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18005e6b0`
- `0x180098aa0`

## import_xrefs

- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x180098ad5`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x180098ad5`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x180098b1b`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x180098b36`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x180098b54`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x180098b1b`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x180098b36`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x180098b54`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x180098b89`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x180098bbb`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x180098b89`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x180098bbb`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x180098b7a`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x180098be0`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x180098c25`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x180098b7a`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x180098be0`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x180098c25`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
struct tagSIZE __fastcall Windows::Internal::DialogRootElement::_SelfLayoutUpdateDesiredSize(
        Windows::Internal::DialogRootElement *this,
        __int64 a2,
        int a3,
        struct DirectUI::Surface *a4)
{
  unsigned int v4; // r14d
  __int64 Children; // rax
  _QWORD *v8; // rcx
  int v9; // edx
  DirectUI::Element *v10; // rbx
  __int64 v11; // rax
  DirectUI::Element *v12; // r13
  DirectUI::Element *v13; // rsi
  const struct tagRECT *v14; // r12
  bool Visible; // al
  int v16; // ecx
  LONG left; // ecx
  int v18; // edi
  int v19; // esi
  bool v20; // bl
  int v21; // edi
  LONG bottom; // edi
  int v23; // r14d
  struct DirectUI::Surface *v24; // r9
  int v25; // eax
  struct DirectUI::Value *v27; // [rsp+30h] [rbp-41h] BYREF
  struct DirectUI::Value *v28; // [rsp+38h] [rbp-39h] BYREF
  struct DirectUI::Value *v29; // [rsp+40h] [rbp-31h] BYREF
  __int64 v30; // [rsp+48h] [rbp-29h] BYREF
  const struct tagRECT *Margin; // [rsp+50h] [rbp-21h]
  DirectUI::Element *v32; // [rsp+58h] [rbp-19h]
  const struct tagRECT *v33; // [rsp+60h] [rbp-11h]
  char v34; // [rsp+68h] [rbp-9h] BYREF
  int v35; // [rsp+6Ch] [rbp-5h]
  char v36; // [rsp+70h] [rbp-1h] BYREF
  int v37; // [rsp+74h] [rbp+3h]
  int v38; // [rsp+D8h] [rbp+67h] BYREF
  int v39; // [rsp+DCh] [rbp+6Bh]

  v4 = (unsigned int)a4;
  *(_QWORD *)a2 = 0;
  *(_DWORD *)a2 = a3;
  v30 = 0;
  Children = DirectUI::Element::GetChildren(this, &v30);
  v8 = (_QWORD *)(Children + 8);
  v9 = *(_DWORD *)Children & 0x10000000;
  v10 = *(DirectUI::Element **)(Children + 8);
  if ( v9 )
  {
    v11 = *(_QWORD *)(Children + 8);
    v10 = *(DirectUI::Element **)v10;
  }
  else
  {
    v11 = Children + 8;
  }
  v12 = *(DirectUI::Element **)(v11 + 8);
  if ( v9 )
    v8 = (_QWORD *)*v8;
  v32 = (DirectUI::Element *)v8[2];
  v13 = v32;
  v29 = 0;
  Margin = DirectUI::Element::GetMargin(v10, &v29);
  v28 = 0;
  v14 = DirectUI::Element::GetMargin(v12, &v28);
  v27 = 0;
  v33 = DirectUI::Element::GetMargin(v13, &v27);
  DirectUI::Element::_UpdateDesiredSize(v10, (unsigned int)&v38, a3, (struct DirectUI::Surface *)v4);
  Visible = DirectUI::Element::GetVisible(v10);
  v16 = 0;
  if ( Visible )
  {
    left = v14->left;
    if ( v14->left <= Margin->right )
      left = Margin->right;
    v16 = v38 + left;
  }
  v18 = a3 - v16;
  v19 = 0;
  if ( v18 >= 0 )
    v19 = v18;
  v20 = DirectUI::Element::GetVisible(v32);
  DirectUI::Element::_UpdateDesiredSize(v32, (unsigned int)&v34, v19, (struct DirectUI::Surface *)v4);
  v21 = 0;
  if ( v20 )
  {
    bottom = v14->bottom;
    if ( bottom <= v33->top )
      bottom = v33->top;
    v21 = v35 + bottom;
  }
  v23 = v4 - v21;
  v24 = 0;
  if ( v23 >= 0 )
    v24 = (struct DirectUI::Surface *)(unsigned int)v23;
  DirectUI::Element::_UpdateDesiredSize(v12, (unsigned int)&v36, v19, v24);
  v25 = v39;
  if ( v21 + v37 > v39 )
    v25 = v21 + v37;
  *(_DWORD *)(a2 + 4) = v25;
  CValuePtr::Release((CValuePtr *)&v27);
  CValuePtr::Release((CValuePtr *)&v28);
  CValuePtr::Release((CValuePtr *)&v29);
  CValuePtr::Release((CValuePtr *)&v30);
  return (struct tagSIZE)a2;
}

```

## disassembly

```asm
0x180098aa0  push    rbp
0x180098aa2  push    rbx
0x180098aa3  push    rsi
0x180098aa4  push    rdi
0x180098aa5  push    r12
0x180098aa7  push    r13
0x180098aa9  push    r14
0x180098aab  push    r15
0x180098aad  lea     rbp, [rsp-17h]
0x180098ab2  sub     rsp, 88h
0x180098ab9  mov     r14d, r9d
0x180098abc  mov     edi, r8d
0x180098abf  mov     r15, rdx
0x180098ac2  xor     eax, eax
0x180098ac4  mov     [rdx], rax
0x180098ac7  mov     [rdx], r8d
0x180098aca  xor     r12d, r12d
0x180098acd  mov     [rbp+4Fh+var_78], r12
0x180098ad1  lea     rdx, [rbp+4Fh+var_78]
0x180098ad5  call    cs:__imp_?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z; DirectUI::Element::GetChildren(DirectUI::Value * *)
0x180098adc  nop     dword ptr [rax+rax+00h]
0x180098ae1  lea     rcx, [rax+8]
0x180098ae5  mov     edx, [rax]
0x180098ae7  and     edx, 10000000h
0x180098aed  mov     rbx, [rcx]
0x180098af0  jz      short loc_180098AFA
0x180098af2  mov     rax, rbx
0x180098af5  mov     rbx, [rbx]
0x180098af8  jmp     short loc_180098AFD
0x180098afa  mov     rax, rcx
0x180098afd  mov     r13, [rax+8]
0x180098b01  test    edx, edx
0x180098b03  jz      short loc_180098B08
0x180098b05  mov     rcx, [rcx]
0x180098b08  mov     rsi, [rcx+10h]
0x180098b0c  mov     [rbp+4Fh+var_68], rsi
0x180098b10  mov     [rbp+4Fh+var_80], r12
0x180098b14  lea     rdx, [rbp+4Fh+var_80]
0x180098b18  mov     rcx, rbx
0x180098b1b  call    cs:__imp_?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z; DirectUI::Element::GetMargin(DirectUI::Value * *)
0x180098b22  nop     dword ptr [rax+rax+00h]
0x180098b27  mov     [rbp+4Fh+var_70], rax
0x180098b2b  mov     [rbp+4Fh+var_88], r12
0x180098b2f  lea     rdx, [rbp+4Fh+var_88]
0x180098b33  mov     rcx, r13
0x180098b36  call    cs:__imp_?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z; DirectUI::Element::GetMargin(DirectUI::Value * *)
0x180098b3d  nop     dword ptr [rax+rax+00h]
0x180098b42  mov     r12, rax
0x180098b45  mov     [rbp+4Fh+var_90], 0
0x180098b4d  lea     rdx, [rbp+4Fh+var_90]
0x180098b51  mov     rcx, rsi
0x180098b54  call    cs:__imp_?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z; DirectUI::Element::GetMargin(DirectUI::Value * *)
0x180098b5b  nop     dword ptr [rax+rax+00h]
0x180098b60  mov     [rbp+4Fh+var_60], rax
0x180098b64  mov     rcx, [rbp+4Fh+arg_20]
0x180098b68  mov     [rsp+0C0h+var_A0], rcx
0x180098b6d  mov     r9d, r14d
0x180098b70  mov     r8d, edi
0x180098b73  lea     rdx, [rbp+4Fh+arg_8]
0x180098b77  mov     rcx, rbx
0x180098b7a  call    cs:__imp_?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z; DirectUI::Element::_UpdateDesiredSize(int,int,DirectUI::Surface *)
0x180098b81  nop     dword ptr [rax+rax+00h]
0x180098b86  mov     rcx, rbx
0x180098b89  call    cs:__imp_?GetVisible@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetVisible(void)
0x180098b90  nop     dword ptr [rax+rax+00h]
0x180098b95  xor     ecx, ecx
0x180098b97  test    al, al
0x180098b99  jz      short loc_180098BAD
0x180098b9b  mov     ecx, [r12]
0x180098b9f  mov     rax, [rbp+4Fh+var_70]
0x180098ba3  cmp     ecx, [rax+8]
0x180098ba6  cmovle  ecx, [rax+8]
0x180098baa  add     ecx, [rbp+4Fh+arg_8]
0x180098bad  sub     edi, ecx
0x180098baf  mov     esi, 0
0x180098bb4  cmovns  esi, edi
0x180098bb7  mov     rcx, [rbp+4Fh+var_68]
0x180098bbb  call    cs:__imp_?GetVisible@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetVisible(void)
0x180098bc2  nop     dword ptr [rax+rax+00h]
0x180098bc7  mov     bl, al
0x180098bc9  mov     rax, [rbp+4Fh+arg_20]
0x180098bcd  mov     [rsp+0C0h+var_A0], rax
0x180098bd2  mov     r9d, r14d
0x180098bd5  mov     r8d, esi
0x180098bd8  lea     rdx, [rbp+4Fh+var_58]
0x180098bdc  mov     rcx, [rbp+4Fh+var_68]
0x180098be0  call    cs:__imp_?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z; DirectUI::Element::_UpdateDesiredSize(int,int,DirectUI::Surface *)
0x180098be7  nop     dword ptr [rax+rax+00h]
0x180098bec  xor     edi, edi
0x180098bee  test    bl, bl
0x180098bf0  jz      short loc_180098C05
0x180098bf2  mov     edi, [r12+0Ch]
0x180098bf7  mov     rax, [rbp+4Fh+var_60]
0x180098bfb  cmp     edi, [rax+4]
0x180098bfe  cmovle  edi, [rax+4]
0x180098c02  add     edi, [rbp+4Fh+var_54]
0x180098c05  sub     r14d, edi
0x180098c08  mov     r9d, 0
0x180098c0e  cmovns  r9d, r14d
0x180098c12  mov     rax, [rbp+4Fh+arg_20]
0x180098c16  mov     [rsp+0C0h+var_A0], rax
0x180098c1b  mov     r8d, esi
0x180098c1e  lea     rdx, [rbp+4Fh+var_50]
0x180098c22  mov     rcx, r13
0x180098c25  call    cs:__imp_?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z; DirectUI::Element::_UpdateDesiredSize(int,int,DirectUI::Surface *)
0x180098c2c  nop     dword ptr [rax+rax+00h]
0x180098c31  mov     ecx, [rbp+4Fh+var_4C]
0x180098c34  add     ecx, edi
0x180098c36  mov     eax, [rbp+4Fh+arg_C]
0x180098c39  cmp     ecx, eax
0x180098c3b  cmovg   eax, ecx
0x180098c3e  mov     [r15+4], eax
0x180098c42  lea     rcx, [rbp+4Fh+var_90]; this
0x180098c46  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x180098c4b  nop
0x180098c4c  lea     rcx, [rbp+4Fh+var_88]; this
0x180098c50  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x180098c55  nop
0x180098c56  lea     rcx, [rbp+4Fh+var_80]; this
0x180098c5a  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x180098c5f  nop
0x180098c60  lea     rcx, [rbp+4Fh+var_78]; this
0x180098c64  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x180098c69  mov     rax, r15
0x180098c6c  add     rsp, 88h
0x180098c73  pop     r15
0x180098c75  pop     r14
0x180098c77  pop     r13
0x180098c79  pop     r12
0x180098c7b  pop     rdi
0x180098c7c  pop     rsi
0x180098c7d  pop     rbx
0x180098c7e  pop     rbp
0x180098c7f  retn
```
