# CInfraConnectPage::UpdateCipherCombo(uint,int)

- ea: `0x18002276c`
- end: `0x180022a4e`
- name: `?UpdateCipherCombo@CInfraConnectPage@@AEAAXIH@Z`
- size: `738`
- prototype: `void(CInfraConnectPage *__hidden this, unsigned int, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180021194`
- `0x1800219d8`

## callees

- `0x1800036ac`
- `0x180008484`
- `0x18002276c`
- `0x180023054`

## import_xrefs

- `USER32!SendMessageW` at `0x180022835`
- `USER32!SendMessageW` at `0x1800228ae`
- `USER32!SendMessageW` at `0x1800228c6`
- `USER32!SendMessageW` at `0x180022916`
- `USER32!SendMessageW` at `0x18002292e`
- `USER32!SendMessageW` at `0x18002294e`
- `USER32!SendMessageW` at `0x18002298f`
- `USER32!SendMessageW` at `0x180022835`
- `USER32!SendMessageW` at `0x1800228ae`
- `USER32!SendMessageW` at `0x1800228c6`
- `USER32!SendMessageW` at `0x180022916`
- `USER32!SendMessageW` at `0x18002292e`
- `USER32!SendMessageW` at `0x18002294e`
- `USER32!SendMessageW` at `0x18002298f`
- `USER32!EnableWindow` at `0x180022964`
- `USER32!EnableWindow` at `0x1800229b2`
- `USER32!EnableWindow` at `0x1800229dc`
- `USER32!EnableWindow` at `0x1800229eb`
- `USER32!EnableWindow` at `0x180022964`
- `USER32!EnableWindow` at `0x1800229b2`
- `USER32!EnableWindow` at `0x1800229dc`
- `USER32!EnableWindow` at `0x1800229eb`
- `USER32!SetWindowTextW` at `0x1800229cd`
- `USER32!SetWindowTextW` at `0x1800229cd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CInfraConnectPage::UpdateCipherCombo(HWND *this, unsigned int a2, int a3)
{
  LPARAM v3; // rbx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  unsigned int v7; // ebp
  unsigned int v8; // r14d
  unsigned int v9; // r15d
  unsigned int v10; // r13d
  LPARAM v11; // rsi
  HWND v12; // rdx
  int v13; // r12d
  unsigned int v14; // eax
  unsigned int v15; // ecx
  HWND v16; // rcx
  BOOL v17; // edx
  unsigned int v18; // [rsp+68h] [rbp+10h]
  LPARAM lParam; // [rsp+78h] [rbp+20h] BYREF

  v3 = a2;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 145) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 19, WPP_1064fdabddc73196039d87943bb008b3_Traceguids);
    v5 = WPP_GLOBAL_Control;
  }
  lParam = (LPARAM)WTL::_atltmpPchNil;
  if ( (_DWORD)v3 == -1 )
  {
    if ( v5 != &WPP_GLOBAL_Control && *((_BYTE *)v5 + 145) && (*((_BYTE *)v5 + 148) & 1) != 0 )
    {
      v6 = 20;
LABEL_35:
      WPP_SF_(v5[17], v6, WPP_1064fdabddc73196039d87943bb008b3_Traceguids);
    }
  }
  else
  {
    v7 = 0;
    v8 = 14;
    v18 = 0;
    v9 = 0;
    v10 = 0;
    SendMessageW(this[39], 0x14Bu, 0, 0);
    v11 = v3;
    v12 = this[34];
    v13 = *((_DWORD *)v12 + 6 * v3);
    *((_BYTE *)this + 1500) = *((_BYTE *)v12 + 24 * v3 + 21);
    if ( v13 == 1 )
      v8 = v3 + 1;
    if ( (unsigned int)v3 < v8 )
    {
      do
      {
        if ( *((_DWORD *)v12 + 6 * v11) == v13 && *((_BYTE *)v12 + 24 * v11 + 8) )
        {
          v14 = v9;
          if ( !*((_BYTE *)v12 + 24 * v11 + 20) )
            v14 = v18;
          v18 = v14;
          WTL::CString::LoadStringW((WTL::CString *)&lParam, *((_DWORD *)v12 + 6 * v11 + 4));
          SendMessageW(this[39], 0x143u, 0, lParam);
          SendMessageW(this[39], 0x151u, v9, v11);
          v12 = this[34];
          v15 = v9;
          if ( *((_DWORD *)this + 374) != *((_DWORD *)v12 + 6 * v11 + 1) )
            v15 = v10;
          v10 = v15;
          ++v9;
        }
        LODWORD(v3) = v3 + 1;
        ++v11;
      }
      while ( (unsigned int)v3 < v8 );
      v7 = v18;
    }
    v16 = this[39];
    if ( a3 )
    {
      SendMessageW(v16, 0x14Eu, v10, 0);
    }
    else
    {
      SendMessageW(v16, 0x14Eu, v7, 0);
      *(_DWORD *)((struct HWND__ *)this + 374) = this[34][6 * SendMessageW(this[39], 0x150u, v7, 0) + 1];
    }
    EnableWindow(this[39], v9 != 1);
    if ( !*((_BYTE *)this + 1505) )
      SendMessageW(this[43], 0xF1u, *((_DWORD *)this + 374) != 0, 0);
    if ( !*((_DWORD *)this + 374) || *((_BYTE *)this + 1500) )
    {
      SetWindowTextW(this[36], &word_180034F94);
      EnableWindow(this[36], 0);
      v17 = 0;
    }
    else
    {
      EnableWindow(this[36], 1);
      v17 = 1;
    }
    EnableWindow(this[37], v17);
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 145) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) != 0 )
    {
      v6 = 21;
      goto LABEL_35;
    }
  }
  WTL::CString::~CString((WTL::CString *)&lParam);
}

```

## disassembly

```asm
0x18002276c  mov     [rsp+arg_0], rbx
0x180022771  mov     [rsp+arg_10], r8d
0x180022776  push    rbp
0x180022777  push    rsi
0x180022778  push    rdi
0x180022779  push    r12
0x18002277b  push    r13
0x18002277d  push    r14
0x18002277f  push    r15
0x180022781  sub     rsp, 20h
0x180022785  mov     ebx, edx
0x180022787  mov     rdi, rcx
0x18002278a  lea     rdx, WPP_GLOBAL_Control
0x180022791  mov     rcx, cs:WPP_GLOBAL_Control
0x180022798  cmp     rcx, rdx
0x18002279b  jz      short loc_1800227D5
0x18002279d  cmp     byte ptr [rcx+91h], 4
0x1800227a4  jb      short loc_1800227D5
0x1800227a6  test    byte ptr [rcx+94h], 1
0x1800227ad  jz      short loc_1800227D5
0x1800227af  mov     edx, 13h
0x1800227b4  lea     r8, WPP_1064fdabddc73196039d87943bb008b3_Traceguids
0x1800227bb  mov     rcx, [rcx+88h]
0x1800227c2  call    WPP_SF_
0x1800227c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800227ce  lea     rdx, WPP_GLOBAL_Control
0x1800227d5  mov     rax, cs:?_atltmpPchNil@WTL@@3PEBGEB; ushort const * const WTL::_atltmpPchNil
0x1800227dc  mov     [rsp+58h+lParam], rax
0x1800227e1  cmp     ebx, 0FFFFFFFFh
0x1800227e4  jnz     short loc_180022813
0x1800227e6  cmp     rcx, rdx
0x1800227e9  jz      loc_180022A2F
0x1800227ef  cmp     byte ptr [rcx+91h], 1
0x1800227f6  jb      loc_180022A2F
0x1800227fc  test    byte ptr [rcx+94h], 1
0x180022803  jz      loc_180022A2F
0x180022809  mov     edx, 14h
0x18002280e  jmp     loc_180022A1B
0x180022813  xor     ebp, ebp
0x180022815  lea     r14d, [rbp+0Eh]
0x180022819  mov     [rsp+58h+arg_8], ebp
0x18002281d  xor     r15d, r15d
0x180022820  xor     r13d, r13d
0x180022823  xor     r9d, r9d; lParam
0x180022826  xor     r8d, r8d; wParam
0x180022829  mov     edx, 14Bh; Msg
0x18002282e  mov     rcx, [rdi+138h]; hWnd
0x180022835  call    cs:__imp_SendMessageW
0x18002283b  mov     rsi, rbx
0x18002283e  mov     rdx, [rdi+110h]
0x180022845  lea     rax, [rbx+rbx*2]
0x180022849  mov     r12d, [rdx+rax*8]
0x18002284d  mov     al, [rdx+rax*8+15h]
0x180022851  mov     [rdi+5DCh], al
0x180022857  cmp     r12d, 1
0x18002285b  jnz     short loc_180022861
0x18002285d  lea     r14d, [rbx+1]
0x180022861  cmp     ebx, r14d
0x180022864  jnb     loc_1800228FC
0x18002286a  lea     rbp, [rsi+rsi*2]
0x18002286e  cmp     [rdx+rbp*8], r12d
0x180022872  jnz     short loc_1800228EA
0x180022874  cmp     byte ptr [rdx+rbp*8+8], 0
0x180022879  jz      short loc_1800228EA
0x18002287b  mov     eax, r15d
0x18002287e  cmp     byte ptr [rdx+rbp*8+14h], 0
0x180022883  cmovz   eax, [rsp+58h+arg_8]
0x180022888  mov     [rsp+58h+arg_8], eax
0x18002288c  mov     edx, [rdx+rbp*8+10h]; uID
0x180022890  lea     rcx, [rsp+58h+lParam]; this
0x180022895  call    ?LoadStringW@CString@WTL@@QEAAHI@Z; WTL::CString::LoadStringW(uint)
0x18002289a  mov     r9, [rsp+58h+lParam]; lParam
0x18002289f  xor     r8d, r8d; wParam
0x1800228a2  mov     edx, 143h; Msg
0x1800228a7  mov     rcx, [rdi+138h]; hWnd
0x1800228ae  call    cs:__imp_SendMessageW
0x1800228b4  mov     r8d, r15d; wParam
0x1800228b7  mov     r9, rsi; lParam
0x1800228ba  mov     edx, 151h; Msg
0x1800228bf  mov     rcx, [rdi+138h]; hWnd
0x1800228c6  call    cs:__imp_SendMessageW
0x1800228cc  mov     rdx, [rdi+110h]
0x1800228d3  mov     ecx, r15d
0x1800228d6  mov     eax, [rdx+rbp*8+4]
0x1800228da  cmp     [rdi+5D8h], eax
0x1800228e0  cmovnz  ecx, r13d
0x1800228e4  mov     r13d, ecx
0x1800228e7  inc     r15d
0x1800228ea  inc     ebx
0x1800228ec  inc     rsi
0x1800228ef  cmp     ebx, r14d
0x1800228f2  jb      loc_18002286A
0x1800228f8  mov     ebp, [rsp+58h+arg_8]
0x1800228fc  mov     rcx, [rdi+138h]; hWnd
0x180022903  xor     esi, esi
0x180022905  xor     r9d, r9d; lParam
0x180022908  mov     edx, 14Eh; Msg
0x18002290d  cmp     [rsp+58h+arg_10], esi
0x180022911  jnz     short loc_18002294B
0x180022913  mov     r8d, ebp; wParam
0x180022916  call    cs:__imp_SendMessageW
0x18002291c  xor     r9d, r9d; lParam
0x18002291f  mov     r8d, ebp; wParam
0x180022922  mov     edx, 150h; Msg
0x180022927  mov     rcx, [rdi+138h]; hWnd
0x18002292e  call    cs:__imp_SendMessageW
0x180022934  lea     rcx, [rax+rax*2]
0x180022938  mov     rax, [rdi+110h]
0x18002293f  mov     ecx, [rax+rcx*8+4]
0x180022943  mov     [rdi+5D8h], ecx
0x180022949  jmp     short loc_180022954
0x18002294b  mov     r8d, r13d; wParam
0x18002294e  call    cs:__imp_SendMessageW
0x180022954  mov     edx, esi
0x180022956  cmp     r15d, 1
0x18002295a  setnz   dl; bEnable
0x18002295d  mov     rcx, [rdi+138h]; hWnd
0x180022964  call    cs:__imp_EnableWindow
0x18002296a  cmp     [rdi+5E1h], sil
0x180022971  jnz     short loc_180022995
0x180022973  mov     r8, rsi
0x180022976  cmp     [rdi+5D8h], esi
0x18002297c  setnz   r8b; wParam
0x180022980  xor     r9d, r9d; lParam
0x180022983  mov     edx, 0F1h; Msg
0x180022988  mov     rcx, [rdi+158h]; hWnd
0x18002298f  call    cs:__imp_SendMessageW
0x180022995  cmp     [rdi+5D8h], esi
0x18002299b  jz      short loc_1800229BF
0x18002299d  cmp     [rdi+5DCh], sil
0x1800229a4  jnz     short loc_1800229BF
0x1800229a6  mov     edx, 1; bEnable
0x1800229ab  mov     rcx, [rdi+120h]; hWnd
0x1800229b2  call    cs:__imp_EnableWindow
0x1800229b8  mov     edx, 1
0x1800229bd  jmp     short loc_1800229E4
0x1800229bf  lea     rdx, word_180034F94; lpString
0x1800229c6  mov     rcx, [rdi+120h]; hWnd
0x1800229cd  call    cs:__imp_SetWindowTextW
0x1800229d3  xor     edx, edx; bEnable
0x1800229d5  mov     rcx, [rdi+120h]; hWnd
0x1800229dc  call    cs:__imp_EnableWindow
0x1800229e2  xor     edx, edx; bEnable
0x1800229e4  mov     rcx, [rdi+128h]; hWnd
0x1800229eb  call    cs:__imp_EnableWindow
0x1800229f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800229f8  lea     rax, WPP_GLOBAL_Control
0x1800229ff  cmp     rcx, rax
0x180022a02  jz      short loc_180022A2F
0x180022a04  cmp     byte ptr [rcx+91h], 4
0x180022a0b  jb      short loc_180022A2F
0x180022a0d  test    byte ptr [rcx+94h], 1
0x180022a14  jz      short loc_180022A2F
0x180022a16  mov     edx, 15h
0x180022a1b  lea     r8, WPP_1064fdabddc73196039d87943bb008b3_Traceguids
0x180022a22  mov     rcx, [rcx+88h]
0x180022a29  call    WPP_SF_
0x180022a2e  nop
0x180022a2f  lea     rcx, [rsp+58h+lParam]; this
0x180022a34  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x180022a39  mov     rbx, [rsp+58h+arg_0]
0x180022a3e  add     rsp, 20h
0x180022a42  pop     r15
0x180022a44  pop     r14
0x180022a46  pop     r13
0x180022a48  pop     r12
0x180022a4a  pop     rdi
0x180022a4b  pop     rsi
0x180022a4c  pop     rbp
0x180022a4d  retn
```
