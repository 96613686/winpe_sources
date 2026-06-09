# InvokeJoinAlertCallbacks

- ea: `0x18001928c`
- end: `0x180019583`
- name: `InvokeJoinAlertCallbacks`
- size: `759`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001ad04`
- `0x18001c1a8`

## callees

- `0x180018dd4`
- `0x18001928c`
- `0x18001b548`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## string_xrefs

- `0x180019367`: `Invoked Join Alert for protocol %x, %x`
- `0x180019487`: `Invoked Join Alert for protocol %x, %x`
- `0x180019430`: `InvokeJoinAlertCallbacks : Could notfind protocol %x, %x`
- `0x180019504`: `Invoked Local Join Alert for protocol %x, %x`

## pseudocode

```c
__int64 __fastcall InvokeJoinAlertCallbacks(__int64 a1, __int64 a2, _DWORD *a3, int a4, __int64 a5)
{
  __int64 result; // rax
  int v9; // ecx
  __int64 i; // rbx
  __int64 *j; // rcx
  unsigned int v12; // r9d
  __int64 v13; // r11
  __int64 v14; // rbx
  __int64 v15; // r9
  __int64 v16; // r8
  __int64 v17; // r8
  __int64 v18; // r9
  int v20; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v21[2044]; // [rsp+54h] [rbp-ACh] BYREF

  v20 = 0;
  result = (__int64)memset_0(v21, 0, sizeof(v21));
  v9 = *(_DWORD *)(a2 + 104);
  if ( v9 )
  {
    if ( *(_DWORD *)(a2 + 40) == 1 )
      result = AddToOutstandingJoinList(
                 v9,
                 *(_DWORD *)(a2 + 108),
                 *(_DWORD *)(a1 + 32),
                 *(_DWORD *)(a1 + 36),
                 a3[4],
                 a3[5],
                 1);
  }
  else if ( *(_DWORD *)(a2 + 40) == 1 )
  {
    for ( i = qword_18002B9A8; (__int64 *)i != &qword_18002B9A8; i = *(_QWORD *)i )
    {
      result = *(unsigned int *)(a5 + 16);
      if ( *(_DWORD *)(i + 16) == (_DWORD)result )
      {
        result = *(unsigned int *)(a5 + 20);
        if ( *(_DWORD *)(i + 20) == (_DWORD)result )
          continue;
      }
      if ( *(_QWORD *)(i + 64) )
      {
        if ( qword_18002B8A8 )
        {
          LOWORD(v20) = 0;
          FormatRRASErrorString(
            &v20,
            L"Invoked Join Alert for protocol %x, %x",
            *(unsigned int *)(i + 16),
            *(unsigned int *)(i + 20));
          ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v20);
        }
        result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, int))(i + 64))(
                   *(unsigned int *)(a2 + 104),
                   *(unsigned int *)(a2 + 108),
                   *(unsigned int *)(a1 + 32),
                   *(unsigned int *)(a1 + 36),
                   1);
      }
    }
  }
  else if ( *(_DWORD *)(a2 + 40) == 2 )
  {
    for ( j = *(__int64 **)(a2 + 48); j != (__int64 *)(a2 + 48); j = (__int64 *)*j )
    {
      v12 = *((_DWORD *)j + 6);
      if ( v12 == *(_DWORD *)(a5 + 16) )
      {
        result = *(unsigned int *)(a5 + 20);
        if ( *((_DWORD *)j + 7) == (_DWORD)result )
          continue;
      }
      result = GetProtocolEntry(&qword_18002B9A8, v12, *((unsigned int *)j + 7));
      v14 = result;
      if ( result )
      {
        if ( *(_DWORD *)(result + 16) != 10 && *(_QWORD *)(result + 64) != v13 )
        {
          if ( qword_18002B8A8 != v13 )
          {
            LOWORD(v20) = v13;
            FormatRRASErrorString(
              &v20,
              L"Invoked Join Alert for protocol %x, %x",
              *(unsigned int *)(result + 16),
              *(unsigned int *)(result + 20));
            ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v20);
          }
          result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, int))(v14 + 64))(
                     *(unsigned int *)(a2 + 104),
                     *(unsigned int *)(a2 + 108),
                     *(unsigned int *)(a1 + 32),
                     *(unsigned int *)(a1 + 36),
                     1);
        }
      }
      else if ( qword_18002B8A8 != v13 )
      {
        v15 = (unsigned int)a3[7];
        v16 = (unsigned int)a3[6];
        LOWORD(v20) = v13;
        FormatRRASErrorString(&v20, L"InvokeJoinAlertCallbacks : Could notfind protocol %x, %x", v16, v15);
        result = ((__int64 (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(
                   gMgmEtwContext,
                   qword_18002B8A8,
                   &v20);
      }
      break;
    }
  }
  if ( a4 )
  {
    v17 = *(unsigned int *)(a5 + 16);
    if ( (_DWORD)v17 != 10 )
    {
      if ( *(_QWORD *)(a5 + 80) )
      {
        if ( qword_18002B8A8 )
        {
          v18 = *(unsigned int *)(a5 + 20);
          LOWORD(v20) = 0;
          FormatRRASErrorString(&v20, L"Invoked Local Join Alert for protocol %x, %x", v17, v18);
          ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v20);
        }
        return (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))(a5 + 80))(
                 *(unsigned int *)(a2 + 104),
                 *(unsigned int *)(a2 + 108),
                 *(unsigned int *)(a1 + 32),
                 *(unsigned int *)(a1 + 36),
                 a3[4],
                 a3[5]);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001928c  push    rbp
0x18001928e  push    rbx
0x18001928f  push    rsi
0x180019290  push    rdi
0x180019291  push    r12
0x180019293  push    r13
0x180019295  push    r15
0x180019297  lea     rbp, [rsp-760h]
0x18001929f  sub     rsp, 860h
0x1800192a6  mov     rax, cs:__security_cookie
0x1800192ad  xor     rax, rsp
0x1800192b0  mov     [rbp+790h+var_40], rax
0x1800192b7  mov     rdi, [rbp+790h+arg_20]
0x1800192be  mov     r13, r8
0x1800192c1  mov     rsi, rdx
0x1800192c4  mov     [rsp+890h+var_850], r9d
0x1800192c9  mov     r15, rcx
0x1800192cc  xor     eax, eax
0x1800192ce  xor     edx, edx; Val
0x1800192d0  mov     [rsp+890h+var_840], eax
0x1800192d4  mov     r8d, 7FCh; Size
0x1800192da  lea     rcx, [rsp+890h+var_83C]; void *
0x1800192df  call    memset_0
0x1800192e4  mov     ecx, [rsi+68h]
0x1800192e7  xor     r11d, r11d
0x1800192ea  test    ecx, ecx
0x1800192ec  jz      short loc_180019325
0x1800192ee  cmp     dword ptr [rsi+28h], 1
0x1800192f2  jnz     loc_1800194DE
0x1800192f8  mov     eax, [r13+14h]
0x1800192fc  mov     r9d, [r15+24h]
0x180019300  mov     r8d, [r15+20h]
0x180019304  mov     edx, [rsi+6Ch]
0x180019307  mov     [rsp+890h+var_860], 1
0x18001930f  mov     [rsp+890h+var_868], eax
0x180019313  mov     eax, [r13+10h]
0x180019317  mov     [rsp+890h+var_870], eax
0x18001931b  call    AddToOutstandingJoinList
0x180019320  jmp     loc_1800194DE
0x180019325  cmp     dword ptr [rsi+28h], 1
0x180019329  jnz     loc_1800193D2
0x18001932f  mov     rbx, cs:qword_18002B9A8
0x180019336  lea     r12, qword_18002B9A8
0x18001933d  jmp     loc_1800193C4
0x180019342  mov     eax, [rdi+10h]
0x180019345  cmp     [rbx+10h], eax
0x180019348  jnz     short loc_180019352
0x18001934a  mov     eax, [rdi+14h]
0x18001934d  cmp     [rbx+14h], eax
0x180019350  jz      short loc_1800193C1
0x180019352  cmp     [rbx+40h], r11
0x180019356  jz      short loc_1800193C1
0x180019358  cmp     cs:qword_18002B8A8, r11
0x18001935f  jz      short loc_18001939F
0x180019361  mov     word ptr [rsp+890h+var_840], r11w
0x180019367  lea     rdx, aInvokedJoinAle; "Invoked Join Alert for protocol %x, %x"
0x18001936e  mov     r9d, [rbx+14h]
0x180019372  lea     rcx, [rsp+890h+var_840]
0x180019377  mov     r8d, [rbx+10h]
0x18001937b  call    FormatRRASErrorString
0x180019380  mov     rdx, cs:qword_18002B8A8
0x180019387  lea     r8, [rsp+890h+var_840]
0x18001938c  mov     rcx, cs:gMgmEtwContext
0x180019393  mov     rax, cs:gMgmTemplateFunc
0x18001939a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001939f  mov     r9d, [r15+24h]
0x1800193a3  mov     r8d, [r15+20h]
0x1800193a7  mov     edx, [rsi+6Ch]
0x1800193aa  mov     ecx, [rsi+68h]
0x1800193ad  mov     rax, [rbx+40h]
0x1800193b1  mov     [rsp+890h+var_870], 1
0x1800193b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193be  xor     r11d, r11d
0x1800193c1  mov     rbx, [rbx]
0x1800193c4  cmp     rbx, r12
0x1800193c7  jnz     loc_180019342
0x1800193cd  jmp     loc_1800194DE
0x1800193d2  cmp     dword ptr [rsi+28h], 2
0x1800193d6  jnz     loc_1800194DE
0x1800193dc  lea     rdx, [rsi+30h]
0x1800193e0  mov     rcx, [rdx]
0x1800193e3  jmp     short loc_1800193FA
0x1800193e5  mov     r9d, [rcx+18h]
0x1800193e9  cmp     r9d, [rdi+10h]
0x1800193ed  jnz     short loc_180019404
0x1800193ef  mov     eax, [rdi+14h]
0x1800193f2  cmp     [rcx+1Ch], eax
0x1800193f5  jnz     short loc_180019404
0x1800193f7  mov     rcx, [rcx]
0x1800193fa  cmp     rcx, rdx
0x1800193fd  jnz     short loc_1800193E5
0x1800193ff  jmp     loc_1800194DE
0x180019404  mov     r8d, [rcx+1Ch]
0x180019408  mov     edx, r9d
0x18001940b  lea     rcx, qword_18002B9A8
0x180019412  call    GetProtocolEntry
0x180019417  mov     rbx, rax
0x18001941a  test    rax, rax
0x18001941d  jnz     short loc_18001946C
0x18001941f  cmp     cs:qword_18002B8A8, r11
0x180019426  jz      loc_1800194DE
0x18001942c  mov     r9d, [r13+1Ch]
0x180019430  lea     rdx, aInvokejoinaler; "InvokeJoinAlertCallbacks : Could notfin"...
0x180019437  mov     r8d, [r13+18h]
0x18001943b  lea     rcx, [rsp+890h+var_840]
0x180019440  mov     word ptr [rsp+890h+var_840], r11w
0x180019446  call    FormatRRASErrorString
0x18001944b  mov     rdx, cs:qword_18002B8A8
0x180019452  lea     r8, [rsp+890h+var_840]
0x180019457  mov     rcx, cs:gMgmEtwContext
0x18001945e  mov     rax, cs:gMgmTemplateFunc
0x180019465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001946a  jmp     short loc_1800194DE
0x18001946c  cmp     dword ptr [rax+10h], 0Ah
0x180019470  jz      short loc_1800194DE
0x180019472  cmp     [rax+40h], r11
0x180019476  jz      short loc_1800194DE
0x180019478  cmp     cs:qword_18002B8A8, r11
0x18001947f  jz      short loc_1800194BF
0x180019481  mov     word ptr [rsp+890h+var_840], r11w
0x180019487  lea     rdx, aInvokedJoinAle; "Invoked Join Alert for protocol %x, %x"
0x18001948e  mov     r9d, [rax+14h]
0x180019492  lea     rcx, [rsp+890h+var_840]
0x180019497  mov     r8d, [rax+10h]
0x18001949b  call    FormatRRASErrorString
0x1800194a0  mov     rdx, cs:qword_18002B8A8
0x1800194a7  lea     r8, [rsp+890h+var_840]
0x1800194ac  mov     rcx, cs:gMgmEtwContext
0x1800194b3  mov     rax, cs:gMgmTemplateFunc
0x1800194ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800194bf  mov     r9d, [r15+24h]
0x1800194c3  mov     r8d, [r15+20h]
0x1800194c7  mov     edx, [rsi+6Ch]
0x1800194ca  mov     ecx, [rsi+68h]
0x1800194cd  mov     rax, [rbx+40h]
0x1800194d1  mov     [rsp+890h+var_870], 1
0x1800194d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800194de  cmp     [rsp+890h+var_850], 0
0x1800194e3  jz      short loc_180019562
0x1800194e5  mov     r8d, [rdi+10h]
0x1800194e9  cmp     r8d, 0Ah
0x1800194ed  jz      short loc_180019562
0x1800194ef  cmp     qword ptr [rdi+50h], 0
0x1800194f4  jz      short loc_180019562
0x1800194f6  cmp     cs:qword_18002B8A8, 0
0x1800194fe  jz      short loc_18001953B
0x180019500  mov     r9d, [rdi+14h]
0x180019504  lea     rdx, aInvokedLocalJo; "Invoked Local Join Alert for protocol %"...
0x18001950b  xor     eax, eax
0x18001950d  lea     rcx, [rsp+890h+var_840]
0x180019512  mov     word ptr [rsp+890h+var_840], ax
0x180019517  call    FormatRRASErrorString
0x18001951c  mov     rdx, cs:qword_18002B8A8
0x180019523  lea     r8, [rsp+890h+var_840]
0x180019528  mov     rcx, cs:gMgmEtwContext
0x18001952f  mov     rax, cs:gMgmTemplateFunc
0x180019536  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001953b  mov     ecx, [r13+14h]
0x18001953f  mov     r9d, [r15+24h]
0x180019543  mov     r8d, [r15+20h]
0x180019547  mov     edx, [rsi+6Ch]
0x18001954a  mov     rax, [rdi+50h]
0x18001954e  mov     [rsp+890h+var_868], ecx
0x180019552  mov     ecx, [r13+10h]
0x180019556  mov     [rsp+890h+var_870], ecx
0x18001955a  mov     ecx, [rsi+68h]
0x18001955d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019562  mov     rcx, [rbp+790h+var_40]
0x180019569  xor     rcx, rsp; StackCookie
0x18001956c  call    __security_check_cookie
0x180019571  add     rsp, 860h
0x180019578  pop     r15
0x18001957a  pop     r13
0x18001957c  pop     r12
0x18001957e  pop     rdi
0x18001957f  pop     rsi
0x180019580  pop     rbx
0x180019581  pop     rbp
0x180019582  retn
```
