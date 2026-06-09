# Windows::UI::Composition::EffectGenerator::GetInputPixelName(Windows::UI::Composition::EffectNode const &,unsigned __int64)

- ea: `0x1800024f0`
- end: `0x180002686`
- name: `?GetInputPixelName@EffectGenerator@Composition@UI@Windows@@QEAAAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBVEffectNode@234@_K@Z`
- size: `406`
- prototype: `__int64 __fastcall(_QWORD *, __int64, unsigned int)`
- caller_count: `22`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800010b0`
- `0x180001200`
- `0x180001410`
- `0x180001950`
- `0x180001da0`
- `0x180002080`
- `0x180006470`
- `0x1800066e0`
- `0x180008550`
- `0x1800088a0`
- `0x18001f220`
- `0x1800259f0`
- `0x180025e20`
- `0x180026770`
- `0x180026c40`
- `0x180027090`
- `0x180027170`
- `0x1800274d0`
- `0x180027810`
- `0x180027cd0`
- `0x180027de0`
- `0x180028920`

## callees

- `0x1800024f0`
- `0x18000268c`
- `0x1800027bc`
- `0x180002858`
- `0x180002a60`
- `0x180004db8`
- `0x1800090a0`
- `0x18001de54`
- `0x180021060`
- `0x18002e010`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180002565`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180002565`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::UI::Composition::EffectGenerator::GetInputPixelName(
        _QWORD *a1,
        __int64 a2,
        unsigned int a3)
{
  __int64 v4; // rcx
  __int64 v5; // r8
  char v6; // al
  int v7; // edi
  unsigned int v8; // eax
  __int64 v9; // rcx
  unsigned __int64 v10; // rcx
  __int64 v12; // rax
  __int64 v13; // rcx
  _WORD *v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rdi
  __int64 v17; // rcx
  _BYTE v18[3]; // [rsp+30h] [rbp-58h] BYREF
  char v19; // [rsp+33h] [rbp-55h]
  _BYTE v20[32]; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v21[32]; // [rsp+58h] [rbp-30h] BYREF

  v4 = a3;
  v5 = *(_QWORD *)(a2 + 8);
  if ( *(_DWORD *)(v5 + 8 * v4) == 1 )
  {
    v10 = *(unsigned int *)(v5 + 8 * v4 + 4);
    if ( (__int64)(a1[7] - a1[6]) >> 5 <= v10 )
      goto LABEL_7;
    return a1[6] + 32 * v10;
  }
  else
  {
    if ( *(_DWORD *)(v5 + 8 * v4) == 2 )
    {
      v6 = 0;
    }
    else
    {
      if ( *(_DWORD *)(v5 + 8 * v4) != 3 )
      {
        std::wstring::wstring(v20, L"Unexpected effect input type.");
        Windows::UI::Composition::OriginateException(v17, v20);
      }
      v6 = 1;
    }
    *(_WORD *)&v18[1] = 0;
    v19 = 0;
    if ( v6 )
    {
      v7 = *(_DWORD *)(v5 + 8 * v4 + 4);
      v8 = v7 + (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*a1 + 16LL) + 24LL))(*a1 + 16LL);
    }
    else
    {
      v8 = *(_DWORD *)(v5 + 8 * v4 + 4);
    }
    v9 = a1[3];
    if ( (a1[4] - v9) >> 3 <= (unsigned __int64)v8 )
    {
LABEL_7:
      std::_Xout_of_range("invalid vector subscript");
      __debugbreak();
    }
    *(_WORD *)v18 = *(_WORD *)(v9 + 8LL * v8) | 0x200;
    v15 = std::map<enum ShaderLinkingArgument,std::string>::_Try_emplace<enum ShaderLinkingArgument const &,>(
            a1 + 9,
            v20,
            v18);
    v16 = *(_QWORD *)v15;
    if ( !*(_QWORD *)(*(_QWORD *)v15 + 56LL) )
    {
      v12 = Windows::UI::Composition::PixelShaderSourceBuilder::DeclareParameter(
              (int)a1 + 88,
              (unsigned int)v21,
              69,
              (unsigned int)"sample",
              0);
      std::string::operator=(v16 + 40, v12);
      std::string::~string(v21);
      v13 = a1[1] + 8LL;
      v14 = *(_WORD **)(a1[1] + 16LL);
      if ( v14 == *(_WORD **)(a1[1] + 24LL) )
      {
        std::vector<enum ShaderLinkingArgument>::_Emplace_reallocate<enum ShaderLinkingArgument &>(v13, v14, v18);
      }
      else
      {
        *v14 = *(_WORD *)v18;
        *(_QWORD *)(v13 + 8) += 2LL;
      }
    }
    return v16 + 40;
  }
}

```

## disassembly

```asm
0x1800024f0  mov     [rsp+arg_18], rbx
0x1800024f5  push    rdi
0x1800024f6  sub     rsp, 80h
0x1800024fd  mov     rax, cs:__security_cookie
0x180002504  xor     rax, rsp
0x180002507  mov     [rsp+88h+var_10], rax
0x18000250c  mov     rbx, rcx
0x18000250f  mov     ecx, r8d
0x180002512  mov     r8, [rdx+8]
0x180002516  mov     edx, [r8+rcx*8]
0x18000251a  sub     edx, 1
0x18000251d  jz      short loc_18000256C
0x18000251f  sub     edx, 1
0x180002522  jnz     loc_18000265D
0x180002528  xor     al, al
0x18000252a  xor     edx, edx
0x18000252c  mov     word ptr [rsp+88h+var_58+1], dx
0x180002531  mov     [rsp+88h+var_55], dl
0x180002535  mov     edi, [r8+rcx*8+4]
0x18000253a  test    al, al
0x18000253c  jnz     loc_180002603
0x180002542  mov     eax, edi
0x180002544  mov     rcx, [rbx+18h]
0x180002548  mov     edx, eax
0x18000254a  mov     rax, [rbx+20h]
0x18000254e  sub     rax, rcx
0x180002551  sar     rax, 3
0x180002555  cmp     rax, rdx
0x180002558  ja      loc_18000261D
0x18000255e  lea     rcx, aInvalidVectorS; "invalid vector subscript"
0x180002565  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18000256b  int     3; Trap to Debugger
0x18000256c  mov     ecx, [r8+rcx*8+4]
0x180002571  mov     rax, [rbx+38h]
0x180002575  sub     rax, [rbx+30h]
0x180002579  sar     rax, 5
0x18000257d  cmp     rax, rcx
0x180002580  jbe     short loc_18000255E
0x180002582  shl     rcx, 5
0x180002586  add     rcx, [rbx+30h]
0x18000258a  mov     rax, rcx
0x18000258d  jmp     short loc_1800025E5
0x18000258f  lea     rcx, [rbx+58h]
0x180002593  mov     [rsp+88h+var_68], 0
0x180002598  lea     r9, aSample; "sample"
0x18000259f  mov     r8d, 45h ; 'E'
0x1800025a5  lea     rdx, [rsp+88h+var_30]
0x1800025aa  call    ?DeclareParameter@PixelShaderSourceBuilder@Composition@UI@Windows@@QEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4DCOMPOSITION_EXPRESSION_TYPE@@PEBD_N@Z; Windows::UI::Composition::PixelShaderSourceBuilder::DeclareParameter(DCOMPOSITION_EXPRESSION_TYPE,char const *,bool)
0x1800025af  mov     rdx, rax
0x1800025b2  lea     rcx, [rdi+28h]
0x1800025b6  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x1800025bb  lea     rcx, [rsp+88h+var_30]; void *
0x1800025c0  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800025c5  mov     rcx, [rbx+8]
0x1800025c9  add     rcx, 8
0x1800025cd  mov     rdx, [rcx+8]
0x1800025d1  cmp     rdx, [rcx+10h]
0x1800025d5  jnz     short loc_18000264E
0x1800025d7  lea     r8, [rsp+88h+var_58]
0x1800025dc  call    ??$_Emplace_reallocate@AEAW4ShaderLinkingArgument@@@?$vector@W4ShaderLinkingArgument@@V?$allocator@W4ShaderLinkingArgument@@@std@@@std@@AEAAPEAW4ShaderLinkingArgument@@QEAW42@AEAW42@@Z; std::vector<ShaderLinkingArgument>::_Emplace_reallocate<ShaderLinkingArgument &>(ShaderLinkingArgument * const,ShaderLinkingArgument &)
0x1800025e1  lea     rax, [rdi+28h]
0x1800025e5  mov     rcx, [rsp+88h+var_10]
0x1800025ea  xor     rcx, rsp; StackCookie
0x1800025ed  call    __security_check_cookie
0x1800025f2  mov     rbx, [rsp+88h+arg_18]
0x1800025fa  add     rsp, 80h
0x180002601  pop     rdi
0x180002602  retn
0x180002603  mov     rcx, [rbx]
0x180002606  add     rcx, 10h
0x18000260a  mov     rax, [rcx]
0x18000260d  mov     rax, [rax+18h]
0x180002611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002616  add     eax, edi
0x180002618  jmp     loc_180002544
0x18000261d  mov     eax, 200h
0x180002622  or      ax, [rcx+rdx*8]
0x180002626  mov     word ptr [rsp+88h+var_58], ax
0x18000262b  lea     rcx, [rbx+48h]
0x18000262f  lea     r8, [rsp+88h+var_58]
0x180002634  lea     rdx, [rsp+88h+var_50]
0x180002639  call    ??$_Try_emplace@AEBW4ShaderLinkingArgument@@$$V@?$map@W4ShaderLinkingArgument@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$less@W4ShaderLinkingArgument@@@3@V?$allocator@U?$pair@$$CBW4ShaderLinkingArgument@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBW4ShaderLinkingArgument@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@PEAX@std@@_N@1@AEBW4ShaderLinkingArgument@@@Z; std::map<ShaderLinkingArgument,std::string>::_Try_emplace<ShaderLinkingArgument const &,>(ShaderLinkingArgument const &)
0x18000263e  mov     rdi, [rax]
0x180002641  cmp     qword ptr [rdi+38h], 0
0x180002646  jz      loc_18000258F
0x18000264c  jmp     short loc_1800025E1
0x18000264e  movzx   eax, word ptr [rsp+88h+var_58]
0x180002653  mov     [rdx], ax
0x180002656  add     qword ptr [rcx+8], 2
0x18000265b  jmp     short loc_1800025E1
0x18000265d  cmp     edx, 1
0x180002660  jz      short loc_18000267F
0x180002662  lea     rdx, aUnexpectedEffe_0; "Unexpected effect input type."
0x180002669  lea     rcx, [rsp+88h+var_50]
0x18000266e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180002673  nop
0x180002674  lea     rdx, [rsp+88h+var_50]
0x180002679  call    ?OriginateException@Composition@UI@Windows@@YAXJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::UI::Composition::OriginateException(long,std::wstring const &)
0x18000267f  mov     al, 1
0x180002681  jmp     loc_18000252A
```
