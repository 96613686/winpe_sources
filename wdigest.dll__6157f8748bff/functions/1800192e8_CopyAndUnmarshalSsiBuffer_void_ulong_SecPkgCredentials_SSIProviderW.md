# CopyAndUnmarshalSsiBuffer(void *,ulong,_SecPkgCredentials_SSIProviderW * *)

- ea: `0x1800192e8`
- end: `0x1800195d6`
- name: `?CopyAndUnmarshalSsiBuffer@@YAJPEAXKPEAPEAU_SecPkgCredentials_SSIProviderW@@@Z`
- size: `750`
- prototype: `int(void *, unsigned int, struct _SecPkgCredentials_SSIProviderW **)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180019f80`

## callees

- `0x1800061a0`
- `0x180009770`
- `0x180011fec`
- `0x1800185b8`
- `0x1800192e8`
- `0x18001a33c`
- `0x1800377bc`
- `0x180038010`

## pseudocode

```c
__int64 __fastcall CopyAndUnmarshalSsiBuffer(char *a1, __int64 a2, struct _SecPkgCredentials_SSIProviderW **a3)
{
  size_t v3; // rsi
  char *v6; // r15
  _QWORD *Memory; // r14
  __int64 v8; // rax
  struct _SecPkgCredentials_SSIProviderW *v9; // rdi
  int v10; // ebx
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rdx
  char *v13; // r11
  unsigned __int16 v14; // r8
  SEC_WCHAR *v15; // r10
  unsigned __int16 v16; // bx
  char *v17; // r9
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rax
  size_t ProviderInfoLength; // r8

  v3 = (unsigned int)a2;
  if ( !a1 || !a3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, (unsigned int)a2, a3);
    goto LABEL_47;
  }
  if ( (unsigned int)(a2 - 24) > 0xFFE8 || (v6 = &a1[(unsigned int)a2], v6 < a1) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        124,
        &WPP_cb7bfd1b4d253ebba43e86b9224572dc_Traceguids,
        (unsigned int)a2);
LABEL_47:
    v10 = -1073741811;
LABEL_48:
    v9 = 0;
    goto LABEL_49;
  }
  Memory = (_QWORD *)DigestAllocateMemory((unsigned int)a2);
  v8 = DigestAllocateMemory((unsigned int)v3);
  v9 = (struct _SecPkgCredentials_SSIProviderW *)v8;
  if ( Memory && v8 )
  {
    v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD *, char *))(*(_QWORD *)&g_LsaFunctions + 80LL))(
            0,
            (unsigned int)v3,
            Memory,
            a1);
    if ( v10 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          126,
          &WPP_cb7bfd1b4d253ebba43e86b9224572dc_Traceguids,
          (unsigned int)v10);
      goto LABEL_37;
    }
    memcpy_0(v9, Memory, v3);
    v11 = *Memory;
    if ( *Memory < (unsigned __int64)(a1 + 24)
      || v11 >= (unsigned __int64)v6
      || (v12 = Memory[2], v12 < (unsigned __int64)(a1 + 24))
      || v12 >= (unsigned __int64)v6 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_32;
      v19 = 127;
    }
    else
    {
      v13 = (char *)Memory + v3;
      v14 = 0;
      v15 = (SEC_WCHAR *)&v9[1];
      v16 = 0;
      v17 = (char *)Memory + v11 - (_QWORD)a1;
      if ( v17 + 1 < (char *)Memory + v3 )
      {
        do
        {
          LOBYTE(v15[v14 / 2u]) = v17[v14];
          HIBYTE(v15[v14 / 2u]) = v17[v14 + 1];
          if ( !v17[v14] && !v17[v14 + 1] )
            break;
          v14 += 2;
          v16 = v14;
        }
        while ( &v17[v14 + 1] < v13 );
      }
      if ( &v17[v16 + 1] < v13 )
      {
        v9->sProviderName = v15;
        v20 = (unsigned __int16)(v14 + 2);
        if ( v9->ProviderInfoLength <= (unsigned int)(v3 - v20 - 24) )
        {
          ProviderInfoLength = v9->ProviderInfoLength;
          v9->ProviderInfo = (char *)v15 + v20;
          memcpy_0((char *)v15 + v20, (char *)Memory + v12 - (_QWORD)a1, ProviderInfoLength);
          v10 = 0;
LABEL_37:
          DigestFreeMemory(Memory);
          goto LABEL_38;
        }
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
LABEL_32:
          v10 = -1073741811;
          goto LABEL_37;
        }
        v19 = 129;
      }
      else
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_32;
        v19 = 128;
      }
    }
    WPP_SF_(v18[2], v19, &WPP_cb7bfd1b4d253ebba43e86b9224572dc_Traceguids);
    goto LABEL_32;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 125, &WPP_cb7bfd1b4d253ebba43e86b9224572dc_Traceguids, 0);
  v10 = -2146893056;
  if ( Memory )
    goto LABEL_37;
LABEL_38:
  if ( v10 )
  {
    if ( v9 )
      DigestFreeMemory(v9);
    goto LABEL_48;
  }
LABEL_49:
  *a3 = v9;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800192e8  push    rbx
0x1800192ea  push    rbp
0x1800192eb  push    rsi
0x1800192ec  push    rdi
0x1800192ed  push    r12
0x1800192ef  push    r13
0x1800192f1  push    r14
0x1800192f3  push    r15
0x1800192f5  sub     rsp, 38h
0x1800192f9  mov     esi, edx
0x1800192fb  mov     r13, r8
0x1800192fe  mov     rbp, rcx
0x180019301  test    rcx, rcx
0x180019304  jz      loc_18001958E
0x18001930a  test    r8, r8
0x18001930d  jz      loc_18001958E
0x180019313  lea     eax, [rsi-18h]
0x180019316  cmp     eax, 0FFE8h
0x18001931b  ja      loc_18001955B
0x180019321  lea     r15, [rsi+rcx]
0x180019325  cmp     r15, rcx
0x180019328  jb      loc_18001955B
0x18001932e  mov     ecx, esi; Size
0x180019330  call    DigestAllocateMemory
0x180019335  mov     ecx, esi; Size
0x180019337  mov     r14, rax
0x18001933a  call    DigestAllocateMemory
0x18001933f  mov     rdi, rax
0x180019342  test    r14, r14
0x180019345  jz      loc_180019505
0x18001934b  test    rax, rax
0x18001934e  jz      loc_180019505
0x180019354  mov     rax, cs:g_LsaFunctions
0x18001935b  mov     r9, rbp
0x18001935e  mov     r8, r14
0x180019361  mov     edx, esi
0x180019363  xor     ecx, ecx
0x180019365  mov     rax, [rax+50h]
0x180019369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001936e  mov     ebx, eax
0x180019370  test    eax, eax
0x180019372  jns     short loc_1800193B2
0x180019374  mov     rcx, cs:WPP_GLOBAL_Control
0x18001937b  lea     rax, WPP_GLOBAL_Control
0x180019382  cmp     rcx, rax
0x180019385  jz      loc_180019540
0x18001938b  test    byte ptr [rcx+1Ch], 1
0x18001938f  jz      loc_180019540
0x180019395  mov     rcx, [rcx+10h]
0x180019399  lea     r8, WPP_cb7bfd1b4d253ebba43e86b9224572dc_Traceguids
0x1800193a0  mov     edx, 7Eh ; '~'
0x1800193a5  mov     r9d, ebx
0x1800193a8  call    WPP_SF_d
0x1800193ad  jmp     loc_180019540
0x1800193b2  mov     r8, rsi; Size
0x1800193b5  mov     rdx, r14; Src
0x1800193b8  mov     rcx, rdi; void *
0x1800193bb  call    memcpy_0
0x1800193c0  mov     rax, [r14]
0x1800193c3  lea     rcx, [rbp+18h]
0x1800193c7  cmp     rax, rcx
0x1800193ca  jb      loc_1800194D0
0x1800193d0  cmp     rax, r15
0x1800193d3  jnb     loc_1800194D0
0x1800193d9  mov     rdx, [r14+10h]
0x1800193dd  cmp     rdx, rcx
0x1800193e0  jb      loc_1800194D0
0x1800193e6  cmp     rdx, r15
0x1800193e9  jnb     loc_1800194D0
0x1800193ef  sub     rax, rbp
0x1800193f2  lea     r11, [rsi+r14]
0x1800193f6  xor     r8d, r8d
0x1800193f9  lea     r10, [rdi+18h]
0x1800193fd  xor     ebx, ebx
0x1800193ff  lea     r9, [rax+r14]
0x180019403  lea     rax, [r9+1]
0x180019407  cmp     rax, r11
0x18001940a  jnb     short loc_180019449
0x18001940c  movzx   ecx, r8w
0x180019410  mov     al, [rcx+r9]
0x180019414  mov     [rcx+r10], al
0x180019418  mov     al, [rcx+r9+1]
0x18001941d  mov     [rcx+r10+1], al
0x180019422  cmp     byte ptr [rcx+r9], 0
0x180019427  jnz     short loc_180019431
0x180019429  cmp     byte ptr [rcx+r9+1], 0
0x18001942f  jz      short loc_180019449
0x180019431  add     r8w, 2
0x180019436  movzx   ecx, r8w
0x18001943a  movzx   ebx, r8w
0x18001943e  inc     rcx
0x180019441  add     rcx, r9
0x180019444  cmp     rcx, r11
0x180019447  jb      short loc_18001940C
0x180019449  movzx   ecx, bx
0x18001944c  inc     rcx
0x18001944f  add     rcx, r9
0x180019452  cmp     rcx, r11
0x180019455  jb      short loc_18001947F
0x180019457  mov     rcx, cs:WPP_GLOBAL_Control
0x18001945e  lea     rax, WPP_GLOBAL_Control
0x180019465  cmp     rcx, rax
0x180019468  jz      loc_1800194FE
0x18001946e  test    byte ptr [rcx+1Ch], 1
0x180019472  jz      loc_1800194FE
0x180019478  mov     edx, 80h
0x18001947d  jmp     short loc_1800194EE
0x18001947f  add     r8w, 2
0x180019484  mov     [rdi], r10
0x180019487  movzx   eax, r8w
0x18001948b  sub     esi, eax
0x18001948d  sub     esi, 18h
0x180019490  cmp     [rdi+8], esi
0x180019493  jbe     short loc_1800194B5
0x180019495  mov     rcx, cs:WPP_GLOBAL_Control
0x18001949c  lea     rax, WPP_GLOBAL_Control
0x1800194a3  cmp     rcx, rax
0x1800194a6  jz      short loc_1800194FE
0x1800194a8  test    byte ptr [rcx+1Ch], 1
0x1800194ac  jz      short loc_1800194FE
0x1800194ae  mov     edx, 81h
0x1800194b3  jmp     short loc_1800194EE
0x1800194b5  mov     r8d, [rdi+8]; Size
0x1800194b9  lea     rcx, [r10+rax]; void *
0x1800194bd  sub     rdx, rbp
0x1800194c0  mov     [rdi+10h], rcx
0x1800194c4  add     rdx, r14; Src
0x1800194c7  call    memcpy_0
0x1800194cc  xor     ebx, ebx
0x1800194ce  jmp     short loc_180019540
0x1800194d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800194d7  lea     rax, WPP_GLOBAL_Control
0x1800194de  cmp     rcx, rax
0x1800194e1  jz      short loc_1800194FE
0x1800194e3  test    byte ptr [rcx+1Ch], 1
0x1800194e7  jz      short loc_1800194FE
0x1800194e9  mov     edx, 7Fh
0x1800194ee  mov     rcx, [rcx+10h]
0x1800194f2  lea     r8, WPP_cb7bfd1b4d253ebba43e86b9224572dc_Traceguids
0x1800194f9  call    WPP_SF_
0x1800194fe  mov     ebx, 0C000000Dh
0x180019503  jmp     short loc_180019540
0x180019505  mov     rcx, cs:WPP_GLOBAL_Control
0x18001950c  lea     rax, WPP_GLOBAL_Control
0x180019513  cmp     rcx, rax
0x180019516  jz      short loc_180019536
0x180019518  test    byte ptr [rcx+1Ch], 1
0x18001951c  jz      short loc_180019536
0x18001951e  mov     rcx, [rcx+10h]
0x180019522  lea     r8, WPP_cb7bfd1b4d253ebba43e86b9224572dc_Traceguids
0x180019529  mov     edx, 7Dh ; '}'
0x18001952e  xor     r9d, r9d
0x180019531  call    WPP_SF_d
0x180019536  mov     ebx, 80090300h
0x18001953b  test    r14, r14
0x18001953e  jz      short loc_180019548
0x180019540  mov     rcx, r14; hMem
0x180019543  call    DigestFreeMemory
0x180019548  test    ebx, ebx
0x18001954a  jz      short loc_1800195BF
0x18001954c  test    rdi, rdi
0x18001954f  jz      short loc_1800195BD
0x180019551  mov     rcx, rdi; hMem
0x180019554  call    DigestFreeMemory
0x180019559  jmp     short loc_1800195BD
0x18001955b  mov     rcx, cs:WPP_GLOBAL_Control
0x180019562  lea     rax, WPP_GLOBAL_Control
0x180019569  cmp     rcx, rax
0x18001956c  jz      short loc_1800195B8
0x18001956e  test    byte ptr [rcx+1Ch], 1
0x180019572  jz      short loc_1800195B8
0x180019574  mov     rcx, [rcx+10h]
0x180019578  lea     r8, WPP_cb7bfd1b4d253ebba43e86b9224572dc_Traceguids
0x18001957f  mov     edx, 7Ch ; '|'
0x180019584  mov     r9d, esi
0x180019587  call    WPP_SF_d
0x18001958c  jmp     short loc_1800195B8
0x18001958e  mov     rcx, cs:WPP_GLOBAL_Control
0x180019595  lea     rax, WPP_GLOBAL_Control
0x18001959c  cmp     rcx, rax
0x18001959f  jz      short loc_1800195B8
0x1800195a1  test    byte ptr [rcx+1Ch], 1
0x1800195a5  jz      short loc_1800195B8
0x1800195a7  mov     rcx, [rcx+10h]
0x1800195ab  mov     r9d, esi
0x1800195ae  mov     [rsp+78h+var_58], r13
0x1800195b3  call    WPP_SF_Dq
0x1800195b8  mov     ebx, 0C000000Dh
0x1800195bd  xor     edi, edi
0x1800195bf  mov     [r13+0], rdi
0x1800195c3  mov     eax, ebx
0x1800195c5  add     rsp, 38h
0x1800195c9  pop     r15
0x1800195cb  pop     r14
0x1800195cd  pop     r13
0x1800195cf  pop     r12
0x1800195d1  pop     rdi
0x1800195d2  pop     rsi
0x1800195d3  pop     rbp
0x1800195d4  pop     rbx
0x1800195d5  retn
```
