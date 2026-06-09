# CBaseFolder::_GetObjectID(ushort const *,ushort *,uint)

- ea: `0x1800050d0`
- end: `0x18000544e`
- name: `?_GetObjectID@CBaseFolder@@QEAAJPEBGPEAGI@Z`
- size: `894`
- prototype: `int(CBaseFolder *__hidden this, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `20`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002cf0`
- `0x180004200`
- `0x180004a80`
- `0x18000e840`
- `0x18000fbd8`
- `0x180016780`
- `0x180017c88`
- `0x18001ff08`
- `0x18002e790`
- `0x180032440`
- `0x18003c074`
- `0x18003cce4`
- `0x18003da14`
- `0x18003e1c0`
- `0x180044b20`
- `0x18004673c`
- `0x180047c14`
- `0x180047f0c`
- `0x180048924`
- `0x180067748`

## callees

- `0x180004110`
- `0x1800050d0`
- `0x18002ff5c`
- `0x180039dd4`
- `0x180039e80`
- `0x180039ef8`
- `0x180078010`

## import_xrefs

- `SHLWAPI!StrCmpIW` at `0x180005328`
- `SHLWAPI!StrCmpIW` at `0x180005328`
- `ole32!PropVariantClear` at `0x1800053af`
- `ole32!PropVariantClear` at `0x1800053af`
- `ole32!CoCreateInstance` at `0x1800051f2`
- `ole32!CoCreateInstance` at `0x1800051f2`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CBaseFolder::_GetObjectID(
        CBaseFolder *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned int a4)
{
  unsigned __int64 v4; // rsi
  int v7; // ebx
  HRESULT v8; // eax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  int v11; // eax
  _QWORD *v12; // rcx
  int v13; // edx
  int v14; // eax
  __int64 v16; // [rsp+30h] [rbp-29h] BYREF
  __int64 v17; // [rsp+38h] [rbp-21h] BYREF
  __int64 v18; // [rsp+40h] [rbp-19h] BYREF
  PROPVARIANT psz2; // [rsp+48h] [rbp-11h] BYREF
  __int128 v20; // [rsp+60h] [rbp+7h] BYREF
  __int64 v21; // [rsp+70h] [rbp+17h]
  LPVOID ppv; // [rsp+C8h] [rbp+6Fh] BYREF

  v4 = a4;
  v18 = 0;
  v17 = 0;
  v16 = 0;
  ppv = 0;
  memset(&psz2, 0, sizeof(psz2));
  v20 = 0;
  v21 = 0;
  if ( !a2 || !a3 || !a4 )
  {
    v7 = -2147024809;
    goto LABEL_42;
  }
  v8 = (*(__int64 (__fastcall **)(CBaseFolder *, _QWORD, __int64 *))(*(_QWORD *)this + 136LL))(
         this,
         *((_QWORD *)this + 8),
         &v18);
  v7 = v8;
  if ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v18 + 40LL))(v18, &v17);
    v7 = v8;
    if ( v8 >= 0 )
    {
      v8 = CoCreateInstance(
             &CLSID_PortableDevicePropVariantCollection,
             0,
             1u,
             &GUID_89b2e422_4f1b_4316_bcef_a44afea83eb3,
             &ppv);
      v7 = v8;
      if ( v8 >= 0 )
      {
        LOWORD(v20) = 31;
        *((_QWORD *)&v20 + 1) = a2;
        v11 = (*(__int64 (__fastcall **)(LPVOID, __int128 *))(*(_QWORD *)ppv + 40LL))(ppv, &v20);
        v7 = v11;
        if ( v11 >= 0 )
        {
          v11 = (*(__int64 (__fastcall **)(__int64, LPVOID, __int64 *))(*(_QWORD *)v17 + 72LL))(v17, ppv, &v16);
          v7 = v11;
          if ( v11 >= 0 )
          {
            v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, PROPVARIANT *))(*(_QWORD *)v16 + 32LL))(v16, 0, &psz2);
            v7 = v8;
            if ( v8 >= 0 )
            {
              if ( psz2.vt == 31 && psz2.hVal.QuadPart && StrCmpIW(&String, psz2.bstrVal) )
              {
                v14 = StringCchCopyW(a3, v4, psz2.bstrVal);
                v7 = v14;
                if ( v14 >= 0 )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
                    WPP_SF_SS(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      47,
                      (unsigned int)WPP_f4dfe53786183352449e3e96734e584d_Traceguids,
                      (_DWORD)a2,
                      (__int64)a3);
                }
                else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  WPP_SF_Sdd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    46,
                    (unsigned int)WPP_f4dfe53786183352449e3e96734e584d_Traceguids,
                    psz2.lVal,
                    v4,
                    v14);
                }
              }
              else
              {
                v7 = -2147418113;
              }
            }
            else
            {
              v9 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                v10 = 45;
                goto LABEL_9;
              }
            }
            goto LABEL_42;
          }
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_42;
          v13 = 44;
        }
        else
        {
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_42;
          v13 = 43;
        }
        WPP_SF_Sd(v12[2], v13, (unsigned int)WPP_f4dfe53786183352449e3e96734e584d_Traceguids, (_DWORD)a2, v11);
        goto LABEL_42;
      }
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v10 = 42;
        goto LABEL_9;
      }
    }
    else
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v10 = 41;
        goto LABEL_9;
      }
    }
  }
  else
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v10 = 40;
LABEL_9:
      WPP_SF_d(v9[2], v10, WPP_f4dfe53786183352449e3e96734e584d_Traceguids, (unsigned int)v8);
    }
  }
LABEL_42:
  PropVariantClear(&psz2);
  if ( v7 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_f4dfe53786183352449e3e96734e584d_Traceguids, (unsigned int)v7);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800050d0  push    rbp
0x1800050d2  push    rbx
0x1800050d3  push    rsi
0x1800050d4  push    rdi
0x1800050d5  push    r12
0x1800050d7  push    r14
0x1800050d9  lea     rbp, [rsp-2Fh]
0x1800050de  sub     rsp, 88h
0x1800050e5  mov     esi, r9d
0x1800050e8  mov     r14, r8
0x1800050eb  mov     rdi, rdx
0x1800050ee  mov     [rbp+57h+var_70], 0
0x1800050f6  mov     [rbp+57h+var_78], 0
0x1800050fe  mov     [rbp+57h+var_80], 0
0x180005106  mov     [rbp+57h+arg_8], 0
0x18000510e  xorps   xmm0, xmm0
0x180005111  xor     eax, eax
0x180005113  movups  xmmword ptr [rbp+57h+psz2], xmm0
0x180005117  mov     [rbp+57h+var_58], rax
0x18000511b  xorps   xmm1, xmm1
0x18000511e  movups  [rbp+57h+var_50], xmm1
0x180005122  mov     [rbp+57h+var_40], rax
0x180005126  lea     r12, WPP_GLOBAL_Control
0x18000512d  test    rdx, rdx
0x180005130  jnz     short loc_18000513C
0x180005132  mov     ebx, 80070057h
0x180005137  jmp     loc_1800053AB
0x18000513c  test    r14, r14
0x18000513f  jz      short loc_180005132
0x180005141  test    r9d, r9d
0x180005144  jz      short loc_180005132
0x180005146  mov     rax, [rcx]
0x180005149  lea     r8, [rbp+57h+var_70]
0x18000514d  mov     rdx, [rcx+40h]
0x180005151  mov     rax, [rax+88h]
0x180005158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000515d  mov     ebx, eax
0x18000515f  test    eax, eax
0x180005161  jns     short loc_18000519A
0x180005163  mov     rcx, cs:WPP_GLOBAL_Control
0x18000516a  cmp     rcx, r12
0x18000516d  jz      loc_1800053AB
0x180005173  test    byte ptr [rcx+1Ch], 2
0x180005177  jz      loc_1800053AB
0x18000517d  mov     edx, 28h ; '('
0x180005182  mov     r9d, eax
0x180005185  lea     r8, WPP_f4dfe53786183352449e3e96734e584d_Traceguids
0x18000518c  mov     rcx, [rcx+10h]
0x180005190  call    WPP_SF_d
0x180005195  jmp     loc_1800053AB
0x18000519a  mov     rcx, [rbp+57h+var_70]
0x18000519e  mov     rax, [rcx]
0x1800051a1  lea     rdx, [rbp+57h+var_78]
0x1800051a5  mov     rax, [rax+28h]
0x1800051a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051ae  mov     ebx, eax
0x1800051b0  test    eax, eax
0x1800051b2  jns     short loc_1800051D5
0x1800051b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800051bb  cmp     rcx, r12
0x1800051be  jz      loc_1800053AB
0x1800051c4  test    byte ptr [rcx+1Ch], 2
0x1800051c8  jz      loc_1800053AB
0x1800051ce  mov     edx, 29h ; ')'
0x1800051d3  jmp     short loc_180005182
0x1800051d5  lea     rax, [rbp+57h+arg_8]
0x1800051d9  mov     [rsp+0B0h+ppv], rax; ppv
0x1800051de  lea     r9, _GUID_89b2e422_4f1b_4316_bcef_a44afea83eb3; riid
0x1800051e5  xor     edx, edx; pUnkOuter
0x1800051e7  lea     r8d, [rdx+1]; dwClsContext
0x1800051eb  lea     rcx, CLSID_PortableDevicePropVariantCollection; rclsid
0x1800051f2  call    cs:__imp_CoCreateInstance
0x1800051f8  mov     ebx, eax
0x1800051fa  test    eax, eax
0x1800051fc  jns     short loc_180005222
0x1800051fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180005205  cmp     rcx, r12
0x180005208  jz      loc_1800053AB
0x18000520e  test    byte ptr [rcx+1Ch], 2
0x180005212  jz      loc_1800053AB
0x180005218  mov     edx, 2Ah ; '*'
0x18000521d  jmp     loc_180005182
0x180005222  mov     eax, 1Fh
0x180005227  mov     word ptr [rbp+57h+var_50], ax
0x18000522b  mov     qword ptr [rbp+57h+var_50+8], rdi
0x18000522f  mov     rcx, [rbp+57h+arg_8]
0x180005233  mov     rax, [rcx]
0x180005236  lea     rdx, [rbp+57h+var_50]
0x18000523a  mov     rax, [rax+28h]
0x18000523e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005243  mov     ebx, eax
0x180005245  test    eax, eax
0x180005247  jns     short loc_180005284
0x180005249  mov     rcx, cs:WPP_GLOBAL_Control
0x180005250  cmp     rcx, r12
0x180005253  jz      loc_1800053AB
0x180005259  test    byte ptr [rcx+1Ch], 2
0x18000525d  jz      loc_1800053AB
0x180005263  mov     edx, 2Bh ; '+'
0x180005268  mov     dword ptr [rsp+0B0h+ppv], eax
0x18000526c  mov     r9, rdi
0x18000526f  lea     r8, WPP_f4dfe53786183352449e3e96734e584d_Traceguids
0x180005276  mov     rcx, [rcx+10h]
0x18000527a  call    WPP_SF_Sd
0x18000527f  jmp     loc_1800053AB
0x180005284  mov     rcx, [rbp+57h+var_78]
0x180005288  mov     rax, [rcx]
0x18000528b  lea     r8, [rbp+57h+var_80]
0x18000528f  mov     rdx, [rbp+57h+arg_8]
0x180005293  mov     rax, [rax+48h]
0x180005297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000529c  mov     ebx, eax
0x18000529e  test    eax, eax
0x1800052a0  jns     short loc_1800052C3
0x1800052a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800052a9  cmp     rcx, r12
0x1800052ac  jz      loc_1800053AB
0x1800052b2  test    byte ptr [rcx+1Ch], 2
0x1800052b6  jz      loc_1800053AB
0x1800052bc  mov     edx, 2Ch ; ','
0x1800052c1  jmp     short loc_180005268
0x1800052c3  mov     rcx, [rbp+57h+var_80]
0x1800052c7  mov     rax, [rcx]
0x1800052ca  lea     r8, [rbp+57h+psz2]
0x1800052ce  xor     edx, edx
0x1800052d0  mov     rax, [rax+20h]
0x1800052d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052d9  mov     ebx, eax
0x1800052db  test    eax, eax
0x1800052dd  jns     short loc_180005303
0x1800052df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800052e6  cmp     rcx, r12
0x1800052e9  jz      loc_1800053AB
0x1800052ef  test    byte ptr [rcx+1Ch], 2
0x1800052f3  jz      loc_1800053AB
0x1800052f9  mov     edx, 2Dh ; '-'
0x1800052fe  jmp     loc_180005182
0x180005303  mov     eax, 1Fh
0x180005308  cmp     ax, word ptr [rbp+57h+psz2]
0x18000530c  jz      short loc_180005318
0x18000530e  mov     ebx, 8000FFFFh
0x180005313  jmp     loc_1800053AB
0x180005318  mov     rdx, [rbp+57h+psz2+8]; psz2
0x18000531c  test    rdx, rdx
0x18000531f  jz      short loc_18000530E
0x180005321  lea     rcx, String; psz1
0x180005328  call    cs:__imp_StrCmpIW
0x18000532e  test    eax, eax
0x180005330  jz      short loc_18000530E
0x180005332  mov     rdx, rsi; unsigned __int64
0x180005335  mov     r8, [rbp+57h+psz2+8]; unsigned __int16 *
0x180005339  mov     rcx, r14; unsigned __int16 *
0x18000533c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180005341  mov     ebx, eax
0x180005343  test    eax, eax
0x180005345  jns     short loc_18000537C
0x180005347  mov     rcx, cs:WPP_GLOBAL_Control
0x18000534e  cmp     rcx, r12
0x180005351  jz      short loc_1800053AB
0x180005353  test    byte ptr [rcx+1Ch], 2
0x180005357  jz      short loc_1800053AB
0x180005359  mov     edx, 2Eh ; '.'
0x18000535e  mov     [rsp+0B0h+var_88], eax
0x180005362  mov     dword ptr [rsp+0B0h+ppv], esi
0x180005366  mov     r9, [rbp+57h+psz2+8]
0x18000536a  lea     r8, WPP_f4dfe53786183352449e3e96734e584d_Traceguids
0x180005371  mov     rcx, [rcx+10h]
0x180005375  call    WPP_SF_Sdd
0x18000537a  jmp     short loc_1800053AB
0x18000537c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005383  cmp     rcx, r12
0x180005386  jz      short loc_1800053AB
0x180005388  test    byte ptr [rcx+1Ch], 40h
0x18000538c  jz      short loc_1800053AB
0x18000538e  mov     edx, 2Fh ; '/'
0x180005393  mov     [rsp+0B0h+ppv], r14
0x180005398  mov     r9, rdi
0x18000539b  lea     r8, WPP_f4dfe53786183352449e3e96734e584d_Traceguids
0x1800053a2  mov     rcx, [rcx+10h]
0x1800053a6  call    WPP_SF_SS
0x1800053ab  lea     rcx, [rbp+57h+psz2]; pvar
0x1800053af  call    cs:__imp_PropVariantClear
0x1800053b5  test    ebx, ebx
0x1800053b7  jns     short loc_1800053E4
0x1800053b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800053c0  cmp     rcx, r12
0x1800053c3  jz      short loc_1800053E4
0x1800053c5  test    byte ptr [rcx+1Ch], 2
0x1800053c9  jz      short loc_1800053E4
0x1800053cb  mov     edx, 30h ; '0'
0x1800053d0  mov     r9d, ebx
0x1800053d3  lea     r8, WPP_f4dfe53786183352449e3e96734e584d_Traceguids
0x1800053da  mov     rcx, [rcx+10h]
0x1800053de  call    WPP_SF_d
0x1800053e3  nop
0x1800053e4  mov     rcx, [rbp+57h+arg_8]
0x1800053e8  test    rcx, rcx
0x1800053eb  jz      short loc_1800053FA
0x1800053ed  mov     rax, [rcx]
0x1800053f0  mov     rax, [rax+10h]
0x1800053f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053f9  nop
0x1800053fa  mov     rcx, [rbp+57h+var_80]
0x1800053fe  test    rcx, rcx
0x180005401  jz      short loc_180005410
0x180005403  mov     rax, [rcx]
0x180005406  mov     rax, [rax+10h]
0x18000540a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000540f  nop
0x180005410  mov     rcx, [rbp+57h+var_78]
0x180005414  test    rcx, rcx
0x180005417  jz      short loc_180005426
0x180005419  mov     rax, [rcx]
0x18000541c  mov     rax, [rax+10h]
0x180005420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005425  nop
0x180005426  mov     rcx, [rbp+57h+var_70]
0x18000542a  test    rcx, rcx
0x18000542d  jz      short loc_18000543C
0x18000542f  mov     rax, [rcx]
0x180005432  mov     rax, [rax+10h]
0x180005436  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000543b  nop
0x18000543c  mov     eax, ebx
0x18000543e  add     rsp, 88h
0x180005445  pop     r14
0x180005447  pop     r12
0x180005449  pop     rdi
0x18000544a  pop     rsi
0x18000544b  pop     rbx
0x18000544c  pop     rbp
0x18000544d  retn
```
