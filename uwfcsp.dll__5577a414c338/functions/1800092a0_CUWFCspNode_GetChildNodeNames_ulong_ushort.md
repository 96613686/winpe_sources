# CUWFCspNode::GetChildNodeNames(ulong *,ushort * * *)

- ea: `0x1800092a0`
- end: `0x1800093cb`
- name: `?GetChildNodeNames@CUWFCspNode@@UEAAJPEAKPEAPEAPEAG@Z`
- size: `299`
- prototype: `__int64 __fastcall(CUWFCspNode *__hidden this, unsigned int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800068f4`
- `0x1800092a0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000933a`
- `OLEAUT32!__imp_SysAllocString` at `0x18000933a`
- `OLEAUT32!__imp_SysFreeString` at `0x180009391`
- `OLEAUT32!__imp_SysFreeString` at `0x180009391`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800093a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800093a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009312`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009312`

## string_xrefs

- `0x180009362`: `onecore\base\uwf\uwfcsp\precomp.h`

## pseudocode

```c
__int64 __fastcall CUWFCspNode::GetChildNodeNames(CUWFCspNode *this, unsigned int *a2, unsigned __int16 ***a3)
{
  __int64 v5; // rbx
  unsigned __int16 **v6; // rax
  unsigned __int16 **v7; // r15
  unsigned int v8; // ebx
  __int64 v9; // rsi
  BSTR v10; // rax
  BSTR *v11; // rsi
  unsigned int v12; // r15d
  __int64 i; // rbp
  OLECHAR *psz[13]; // [rsp+20h] [rbp-68h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  if ( a2 && a3 )
  {
    *a2 = 0;
    psz[0] = L"CurrentSession";
    v5 = 40;
    *a3 = 0;
    psz[1] = L"NextSession";
    psz[2] = L"ResetSettings";
    psz[3] = L"ShutdownSystem";
    psz[4] = L"RestartSystem";
    v6 = (unsigned __int16 **)CoTaskMemAlloc(0x28u);
    v7 = v6;
    if ( v6 )
    {
      v9 = 0;
      do
      {
        *(_BYTE *)v6 = 0;
        v6 = (unsigned __int16 **)((char *)v6 + 1);
        --v5;
      }
      while ( v5 );
      while ( 1 )
      {
        v10 = SysAllocString(psz[v9]);
        v7[v9] = v10;
        if ( !v10 )
          break;
        v9 = (unsigned int)(v9 + 1);
        if ( (unsigned int)v9 >= 5 )
        {
          *a3 = v7;
          v8 = 0;
          *a2 = v9;
          return v8;
        }
      }
      v8 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9E,
        (unsigned int)"onecore\\base\\uwf\\uwfcsp\\precomp.h",
        (const char *)0x8007000ELL,
        (int)psz[0]);
    }
    else
    {
      v8 = -2147024882;
    }
    v11 = *a3;
    if ( *a3 )
    {
      v12 = *a2;
      for ( i = 0; (unsigned int)i < v12; i = (unsigned int)(i + 1) )
        SysFreeString(v11[i]);
      CoTaskMemFree(v11);
    }
    *a3 = 0;
    *a2 = 0;
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v8;
}

```

## disassembly

```asm
0x1800092a0  mov     r11, rsp
0x1800092a3  push    rbx
0x1800092a4  push    rbp
0x1800092a5  push    rsi
0x1800092a6  push    rdi
0x1800092a7  push    r14
0x1800092a9  push    r15
0x1800092ab  sub     rsp, 58h
0x1800092af  mov     rdi, r8
0x1800092b2  mov     r14, rdx
0x1800092b5  test    rdx, rdx
0x1800092b8  jz      loc_1800093B7
0x1800092be  test    r8, r8
0x1800092c1  jz      loc_1800093B7
0x1800092c7  lea     rax, aCurrentsession; "CurrentSession"
0x1800092ce  mov     dword ptr [rdx], 0
0x1800092d4  mov     [r11-68h], rax
0x1800092d8  mov     ebx, 28h ; '('
0x1800092dd  lea     rax, aNextsession; "NextSession"
0x1800092e4  mov     qword ptr [r8], 0
0x1800092eb  mov     [r11-60h], rax
0x1800092ef  mov     ecx, ebx; cb
0x1800092f1  lea     rax, aResetsettings; "ResetSettings"
0x1800092f8  mov     [r11-58h], rax
0x1800092fc  lea     rax, aShutdownsystem; "ShutdownSystem"
0x180009303  mov     [r11-50h], rax
0x180009307  lea     rax, aRestartsystem; "RestartSystem"
0x18000930e  mov     [r11-48h], rax
0x180009312  call    cs:__imp_CoTaskMemAlloc
0x180009318  mov     r15, rax
0x18000931b  test    rax, rax
0x18000931e  jnz     short loc_180009327
0x180009320  mov     ebx, 8007000Eh
0x180009325  jmp     short loc_18000937B
0x180009327  xor     esi, esi
0x180009329  mov     [rax], sil
0x18000932c  inc     rax
0x18000932f  sub     rbx, 1
0x180009333  jnz     short loc_180009329
0x180009335  mov     rcx, [rsp+rsi*8+88h+psz]; psz
0x18000933a  call    cs:__imp_SysAllocString
0x180009340  mov     [r15+rsi*8], rax
0x180009344  test    rax, rax
0x180009347  jz      short loc_18000935A
0x180009349  inc     esi
0x18000934b  cmp     esi, 5
0x18000934e  jb      short loc_180009335
0x180009350  mov     [rdi], r15
0x180009353  xor     ebx, ebx
0x180009355  mov     [r14], esi
0x180009358  jmp     short loc_1800093BC
0x18000935a  mov     rcx, [rsp+88h]; this
0x180009362  lea     r8, aOnecoreBaseUwf; "onecore\\base\\uwf\\uwfcsp\\precomp.h"
0x180009369  mov     ebx, 8007000Eh
0x18000936e  mov     edx, 9Eh; void *
0x180009373  mov     r9d, ebx; char *
0x180009376  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000937b  mov     rsi, [rdi]
0x18000937e  test    rsi, rsi
0x180009381  jz      short loc_1800093A7
0x180009383  mov     r15d, [r14]
0x180009386  xor     ebp, ebp
0x180009388  test    r15d, r15d
0x18000938b  jz      short loc_18000939E
0x18000938d  mov     rcx, [rsi+rbp*8]; bstrString
0x180009391  call    cs:__imp_SysFreeString
0x180009397  inc     ebp
0x180009399  cmp     ebp, r15d
0x18000939c  jb      short loc_18000938D
0x18000939e  mov     rcx, rsi; pv
0x1800093a1  call    cs:__imp_CoTaskMemFree
0x1800093a7  mov     qword ptr [rdi], 0
0x1800093ae  mov     dword ptr [r14], 0
0x1800093b5  jmp     short loc_1800093BC
0x1800093b7  mov     ebx, 80070057h
0x1800093bc  mov     eax, ebx
0x1800093be  add     rsp, 58h
0x1800093c2  pop     r15
0x1800093c4  pop     r14
0x1800093c6  pop     rdi
0x1800093c7  pop     rsi
0x1800093c8  pop     rbp
0x1800093c9  pop     rbx
0x1800093ca  retn
```
