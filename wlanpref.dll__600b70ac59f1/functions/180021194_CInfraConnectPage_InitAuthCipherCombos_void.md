# CInfraConnectPage::InitAuthCipherCombos(void)

- ea: `0x180021194`
- end: `0x1800213b8`
- name: `?InitAuthCipherCombos@CInfraConnectPage@@AEAAXXZ`
- size: `548`
- prototype: `void __fastcall(CInfraConnectPage *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180021a70`

## callees

- `0x1800036ac`
- `0x180008484`
- `0x180021194`
- `0x18002276c`
- `0x180023054`

## import_xrefs

- `USER32!SendMessageW` at `0x180021213`
- `USER32!SendMessageW` at `0x180021284`
- `USER32!SendMessageW` at `0x18002129c`
- `USER32!SendMessageW` at `0x180021322`
- `USER32!SendMessageW` at `0x180021213`
- `USER32!SendMessageW` at `0x180021284`
- `USER32!SendMessageW` at `0x18002129c`
- `USER32!SendMessageW` at `0x180021322`
- `USER32!EnableWindow` at `0x180021344`
- `USER32!EnableWindow` at `0x180021353`
- `USER32!EnableWindow` at `0x180021344`
- `USER32!EnableWindow` at `0x180021353`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CInfraConnectPage::InitAuthCipherCombos(HWND *this)
{
  unsigned int v2; // r15d
  int v3; // r12d
  int v4; // ebp
  unsigned int v5; // edi
  LPARAM v6; // r14
  HWND v7; // rdx
  __int64 v8; // rcx
  int v9; // r9d
  int v10; // ecx
  HWND v11; // rax
  bool v12; // dl
  LPARAM lParam; // [rsp+50h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 145) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 17, WPP_1064fdabddc73196039d87943bb008b3_Traceguids);
  }
  lParam = (LPARAM)WTL::_atltmpPchNil;
  v2 = -1;
  v3 = -1;
  v4 = 0;
  SendMessageW(this[38], 0x14Bu, 0, 0);
  v5 = 0;
  v6 = 0;
  do
  {
    v7 = this[34];
    if ( *((_BYTE *)v7 + 24 * v6 + 8) )
    {
      v8 = v5 - 1;
      if ( (int)v8 < 0 )
        goto LABEL_14;
      v9 = *((_DWORD *)v7 + 6 * v6);
      while ( *((_DWORD *)v7 + 6 * v8) != v9 || !*((_BYTE *)v7 + 24 * v8 + 8) )
      {
        v8 = (unsigned int)(v8 - 1);
        if ( (int)v8 < 0 )
          goto LABEL_14;
      }
      if ( v9 == 1 )
      {
LABEL_14:
        WTL::CString::LoadStringW((WTL::CString *)&lParam, *((_DWORD *)v7 + 6 * v6 + 3));
        SendMessageW(this[38], 0x143u, 0, lParam);
        SendMessageW(this[38], 0x151u, v4, v6);
        v10 = *((_DWORD *)this + 373);
        v11 = this[34];
        if ( v10 == *((_DWORD *)v11 + 6 * v6) )
        {
          if ( !*((_BYTE *)this + 1500) || *((_BYTE *)v11 + 24 * v6 + 21) )
          {
            v12 = 1;
            if ( v10 == 1 )
              v12 = *((_DWORD *)this + 374) == *((_DWORD *)v11 + 6 * v6 + 1);
          }
          else
          {
            v12 = 0;
          }
          if ( v3 == -1 && v12 )
          {
            v3 = v4;
            v2 = v5;
          }
        }
        ++v4;
      }
    }
    ++v5;
    ++v6;
  }
  while ( v5 < 0xE );
  if ( v2 == -1 || *((_BYTE *)this + 1506) )
  {
    EnableWindow(this[36], 0);
    EnableWindow(this[39], 0);
  }
  else
  {
    SendMessageW(this[38], 0x14Eu, v3, 0);
    CInfraConnectPage::UpdateCipherCombo(this, v2, 1);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 145) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 18, WPP_1064fdabddc73196039d87943bb008b3_Traceguids);
  }
  WTL::CString::~CString((WTL::CString *)&lParam);
}

```

## disassembly

```asm
0x180021194  mov     [rsp+arg_8], rbx
0x180021199  mov     [rsp+arg_10], rbp
0x18002119e  push    rsi
0x18002119f  push    rdi
0x1800211a0  push    r12
0x1800211a2  push    r14
0x1800211a4  push    r15
0x1800211a6  sub     rsp, 20h
0x1800211aa  mov     rbx, rcx
0x1800211ad  lea     rax, WPP_GLOBAL_Control
0x1800211b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800211bb  cmp     rcx, rax
0x1800211be  jz      short loc_1800211EA
0x1800211c0  cmp     byte ptr [rcx+91h], 4
0x1800211c7  jb      short loc_1800211EA
0x1800211c9  test    byte ptr [rcx+94h], 1
0x1800211d0  jz      short loc_1800211EA
0x1800211d2  mov     edx, 11h
0x1800211d7  lea     r8, WPP_1064fdabddc73196039d87943bb008b3_Traceguids
0x1800211de  mov     rcx, [rcx+88h]
0x1800211e5  call    WPP_SF_
0x1800211ea  mov     rax, cs:?_atltmpPchNil@WTL@@3PEBGEB; ushort const * const WTL::_atltmpPchNil
0x1800211f1  mov     [rsp+48h+lParam], rax
0x1800211f6  or      eax, 0FFFFFFFFh
0x1800211f9  mov     r15d, eax
0x1800211fc  mov     r12d, eax
0x1800211ff  xor     ebp, ebp
0x180021201  xor     r9d, r9d; lParam
0x180021204  xor     r8d, r8d; wParam
0x180021207  mov     edx, 14Bh; Msg
0x18002120c  mov     rcx, [rbx+130h]; hWnd
0x180021213  call    cs:__imp_SendMessageW
0x180021219  xor     edi, edi
0x18002121b  xor     r14d, r14d
0x18002121e  lea     rsi, [r14+r14*2]
0x180021222  mov     rdx, [rbx+110h]
0x180021229  cmp     byte ptr [rdx+rsi*8+8], 0
0x18002122e  jz      loc_1800212F3
0x180021234  lea     ecx, [rdi-1]
0x180021237  test    ecx, ecx
0x180021239  js      short loc_180021262
0x18002123b  mov     r9d, [rdx+rsi*8]
0x18002123f  lea     r8, [rcx+rcx*2]
0x180021243  cmp     [rdx+r8*8], r9d
0x180021247  jnz     short loc_180021251
0x180021249  cmp     byte ptr [rdx+r8*8+8], 0
0x18002124f  jnz     short loc_180021258
0x180021251  sub     ecx, 1
0x180021254  jns     short loc_18002123F
0x180021256  jmp     short loc_180021262
0x180021258  cmp     r9d, 1
0x18002125c  jnz     loc_1800212F3
0x180021262  mov     edx, [rdx+rsi*8+0Ch]; uID
0x180021266  lea     rcx, [rsp+48h+lParam]; this
0x18002126b  call    ?LoadStringW@CString@WTL@@QEAAHI@Z; WTL::CString::LoadStringW(uint)
0x180021270  mov     r9, [rsp+48h+lParam]; lParam
0x180021275  xor     r8d, r8d; wParam
0x180021278  mov     edx, 143h; Msg
0x18002127d  mov     rcx, [rbx+130h]; hWnd
0x180021284  call    cs:__imp_SendMessageW
0x18002128a  movsxd  r8, ebp; wParam
0x18002128d  mov     r9, r14; lParam
0x180021290  mov     edx, 151h; Msg
0x180021295  mov     rcx, [rbx+130h]; hWnd
0x18002129c  call    cs:__imp_SendMessageW
0x1800212a2  mov     ecx, [rbx+5D4h]
0x1800212a8  mov     rax, [rbx+110h]
0x1800212af  cmp     ecx, [rax+rsi*8]
0x1800212b2  jnz     short loc_1800212F1
0x1800212b4  cmp     byte ptr [rbx+5DCh], 0
0x1800212bb  jz      short loc_1800212C8
0x1800212bd  cmp     byte ptr [rax+rsi*8+15h], 0
0x1800212c2  jnz     short loc_1800212C8
0x1800212c4  xor     dl, dl
0x1800212c6  jmp     short loc_1800212E1
0x1800212c8  mov     dl, 1
0x1800212ca  cmp     ecx, 1
0x1800212cd  jnz     short loc_1800212E1
0x1800212cf  movzx   edx, dl
0x1800212d2  xor     ecx, ecx
0x1800212d4  mov     eax, [rax+rsi*8+4]
0x1800212d8  cmp     [rbx+5D8h], eax
0x1800212de  cmovnz  edx, ecx
0x1800212e1  cmp     r12d, 0FFFFFFFFh
0x1800212e5  jnz     short loc_1800212F1
0x1800212e7  test    dl, dl
0x1800212e9  jz      short loc_1800212F1
0x1800212eb  mov     r12d, ebp
0x1800212ee  mov     r15d, edi
0x1800212f1  inc     ebp
0x1800212f3  inc     edi
0x1800212f5  inc     r14
0x1800212f8  cmp     edi, 0Eh
0x1800212fb  jb      loc_18002121E
0x180021301  cmp     r15d, 0FFFFFFFFh
0x180021305  jz      short loc_18002133B
0x180021307  cmp     byte ptr [rbx+5E2h], 0
0x18002130e  jnz     short loc_18002133B
0x180021310  movsxd  r8, r12d; wParam
0x180021313  xor     r9d, r9d; lParam
0x180021316  mov     edx, 14Eh; Msg
0x18002131b  mov     rcx, [rbx+130h]; hWnd
0x180021322  call    cs:__imp_SendMessageW
0x180021328  mov     r8d, 1; int
0x18002132e  mov     edx, r15d; unsigned int
0x180021331  mov     rcx, rbx; this
0x180021334  call    ?UpdateCipherCombo@CInfraConnectPage@@AEAAXIH@Z; CInfraConnectPage::UpdateCipherCombo(uint,int)
0x180021339  jmp     short loc_180021359
0x18002133b  xor     edx, edx; bEnable
0x18002133d  mov     rcx, [rbx+120h]; hWnd
0x180021344  call    cs:__imp_EnableWindow
0x18002134a  xor     edx, edx; bEnable
0x18002134c  mov     rcx, [rbx+138h]; hWnd
0x180021353  call    cs:__imp_EnableWindow
0x180021359  mov     rcx, cs:WPP_GLOBAL_Control
0x180021360  lea     rax, WPP_GLOBAL_Control
0x180021367  cmp     rcx, rax
0x18002136a  jz      short loc_180021397
0x18002136c  cmp     byte ptr [rcx+91h], 4
0x180021373  jb      short loc_180021397
0x180021375  test    byte ptr [rcx+94h], 1
0x18002137c  jz      short loc_180021397
0x18002137e  mov     edx, 12h
0x180021383  lea     r8, WPP_1064fdabddc73196039d87943bb008b3_Traceguids
0x18002138a  mov     rcx, [rcx+88h]
0x180021391  call    WPP_SF_
0x180021396  nop
0x180021397  lea     rcx, [rsp+48h+lParam]; this
0x18002139c  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x1800213a1  mov     rbx, [rsp+48h+arg_8]
0x1800213a6  mov     rbp, [rsp+48h+arg_10]
0x1800213ab  add     rsp, 20h
0x1800213af  pop     r15
0x1800213b1  pop     r14
0x1800213b3  pop     r12
0x1800213b5  pop     rdi
0x1800213b6  pop     rsi
0x1800213b7  retn
```
