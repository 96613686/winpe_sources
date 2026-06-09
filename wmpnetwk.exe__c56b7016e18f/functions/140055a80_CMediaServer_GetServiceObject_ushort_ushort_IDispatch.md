# CMediaServer::GetServiceObject(ushort *,ushort *,IDispatch * *)

- ea: `0x140055a80`
- end: `0x140055d90`
- name: `?GetServiceObject@CMediaServer@@UEAAJPEAG0PEAPEAUIDispatch@@@Z`
- size: `784`
- prototype: `int(CMediaServer *__hidden this, unsigned __int16 *, unsigned __int16 *, struct IDispatch **)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x140006d70`
- `0x14000c920`
- `0x14003e5f4`
- `0x14003f17c`
- `0x14003f1bc`
- `0x140047798`
- `0x140054534`
- `0x140055a80`
- `0x140057660`
- `0x14009e010`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x140055b1a`
- `KERNEL32!CompareStringW` at `0x140055ba6`
- `KERNEL32!CompareStringW` at `0x140055b1a`
- `KERNEL32!CompareStringW` at `0x140055ba6`

## pseudocode

```c
__int64 __fastcall CMediaServer::GetServiceObject(PCNZWCH *this, unsigned __int16 *a2, char *a3, struct IDispatch **a4)
{
  PVOID *v8; // rax
  int v9; // esi
  const WCHAR *v10; // rbx
  int i; // ebp
  unsigned int v12; // ebx
  PVOID *v13; // rcx
  int v14; // esi
  struct IDispatch *v15; // rcx
  __int64 v16; // rdx
  struct IDispatch *v17; // rcx
  struct IDispatch *v18; // rcx
  PCNZWCH v20; // [rsp+78h] [rbp+20h] BYREF

  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_SSq(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a3, (char)a4);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a4 || !a3 )
  {
    if ( v8 == &WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 2) == 0 || *((_BYTE *)v8 + 25) < 2u )
      goto LABEL_52;
    WPP_SF_(v8[2], 31, &WPP_02c6dcd2c5d83623206397dda38e97d9_Traceguids);
    goto LABEL_51;
  }
  v9 = -1;
  if ( a2 && CompareStringW(0x7Fu, 1u, this[10], -1, a2, -1) != 2 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_52;
    }
    WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a2);
LABEL_51:
    v8 = (PVOID *)WPP_GLOBAL_Control;
LABEL_52:
    v12 = -2147024809;
    goto LABEL_53;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    (void **)&v20,
    a3);
  v10 = v20;
  for ( i = 0; ; ++i )
  {
    if ( i >= 3 )
    {
      v13 = (PVOID *)WPP_GLOBAL_Control;
LABEL_24:
      if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 2) != 0 && *((_BYTE *)v13 + 25) >= 2u )
        WPP_SF_S(v13[2], 34, &WPP_02c6dcd2c5d83623206397dda38e97d9_Traceguids, a3);
      v12 = -2147024809;
      goto LABEL_29;
    }
    if ( CompareStringW(0x7Fu, 1u, (PCNZWCH)(&CMediaServer::s_astrServices)[i], -1, v10, -1) == 2 )
      break;
  }
  v12 = 0;
  v9 = i;
  v13 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_02c6dcd2c5d83623206397dda38e97d9_Traceguids, (unsigned int)i);
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( i == -1 )
    goto LABEL_24;
LABEL_29:
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v20);
  if ( (v12 & 0x80000000) != 0 )
    goto LABEL_38;
  if ( !v9 )
  {
    v18 = (struct IDispatch *)this[12];
    *a4 = v18;
    ((void (__fastcall *)(struct IDispatch *))v18->lpVtbl->AddRef)(v18);
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v12;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      goto LABEL_53;
    v16 = 35;
    goto LABEL_37;
  }
  v14 = v9 - 1;
  if ( !v14 )
  {
    v17 = (struct IDispatch *)this[13];
    *a4 = v17;
    ((void (__fastcall *)(struct IDispatch *))v17->lpVtbl->AddRef)(v17);
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v12;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      goto LABEL_53;
    v16 = 36;
    goto LABEL_37;
  }
  if ( v14 != 1 )
  {
LABEL_38:
    v8 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_53;
  }
  v15 = (struct IDispatch *)this[14];
  *a4 = v15;
  ((void (__fastcall *)(struct IDispatch *))v15->lpVtbl->AddRef)(v15);
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v12;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v16 = 37;
LABEL_37:
    WPP_SF_q(v8[2], v16, &WPP_02c6dcd2c5d83623206397dda38e97d9_Traceguids, *a4);
    goto LABEL_38;
  }
LABEL_53:
  if ( v8 != &WPP_GLOBAL_Control
    && (*((_BYTE *)v8 + 28) & 1) != 0
    && *((unsigned __int8 *)v8 + 25) >= (((int)v12 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(v8[2], 38, &WPP_02c6dcd2c5d83623206397dda38e97d9_Traceguids, v12);
  }
  return v12;
}

```

## disassembly

```asm
0x140055a80  mov     r11, rsp
0x140055a83  mov     [r11+8], rbx
0x140055a87  mov     [r11+10h], rbp
0x140055a8b  push    rsi
0x140055a8c  push    r12
0x140055a8e  push    r13
0x140055a90  push    r14
0x140055a92  push    r15
0x140055a94  sub     rsp, 30h
0x140055a98  mov     r14, r9
0x140055a9b  mov     r15, r8
0x140055a9e  mov     rbx, rdx
0x140055aa1  mov     r13, rcx
0x140055aa4  mov     rax, cs:WPP_GLOBAL_Control
0x140055aab  lea     r12, WPP_GLOBAL_Control
0x140055ab2  cmp     rax, r12
0x140055ab5  jz      short loc_140055AEA
0x140055ab7  test    byte ptr [rax+1Ch], 1
0x140055abb  jz      short loc_140055AEA
0x140055abd  cmp     byte ptr [rax+19h], 5
0x140055ac1  jb      short loc_140055AEA
0x140055ac3  mov     rcx, [rax+10h]; LoggerHandle
0x140055ac7  mov     edx, 1Eh
0x140055acc  mov     [r11-30h], r9
0x140055ad0  mov     r9, rbx
0x140055ad3  mov     [r11-38h], r8
0x140055ad7  lea     r8, WPP_02c6dcd2c5d83623206397dda38e97d9_Traceguids
0x140055ade  call    WPP_SF_SSq
0x140055ae3  mov     rax, cs:WPP_GLOBAL_Control
0x140055aea  test    r14, r14
0x140055aed  jz      loc_140055D0E
0x140055af3  test    r15, r15
0x140055af6  jz      loc_140055D0E
0x140055afc  or      esi, 0FFFFFFFFh
0x140055aff  test    rbx, rbx
0x140055b02  jz      short loc_140055B6A
0x140055b04  mov     r8, [r13+50h]; lpString1
0x140055b08  lea     edx, [rsi+2]; dwCmpFlags
0x140055b0b  lea     ecx, [rdx+7Eh]; Locale
0x140055b0e  mov     [rsp+58h+cchCount2], esi; cchCount2
0x140055b12  mov     r9d, esi; cchCount1
0x140055b15  mov     [rsp+58h+lpString2], rbx; lpString2
0x140055b1a  call    cs:__imp_CompareStringW
0x140055b20  cmp     eax, 2
0x140055b23  jz      short loc_140055B6A
0x140055b25  mov     rax, cs:WPP_GLOBAL_Control
0x140055b2c  cmp     rax, r12
0x140055b2f  jz      loc_140055D3B
0x140055b35  test    byte ptr [rax+1Ch], 2
0x140055b39  jz      loc_140055D3B
0x140055b3f  cmp     byte ptr [rax+19h], 2
0x140055b43  jb      loc_140055D3B
0x140055b49  mov     r9, [r13+50h]
0x140055b4d  lea     edx, [rsi+21h]
0x140055b50  mov     rcx, [rax+10h]; LoggerHandle
0x140055b54  lea     r8, WPP_02c6dcd2c5d83623206397dda38e97d9_Traceguids
0x140055b5b  mov     [rsp+58h+lpString2], rbx; __int64
0x140055b60  call    WPP_SF_SS
0x140055b65  jmp     loc_140055D34
0x140055b6a  mov     rdx, r15
0x140055b6d  lea     rcx, [rsp+58h+arg_18]
0x140055b72  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x140055b77  mov     rbx, [rsp+58h+arg_18]
0x140055b7c  xor     ebp, ebp
0x140055b7e  cmp     ebp, 3
0x140055b81  jge     short loc_140055BF5
0x140055b83  or      ecx, 0FFFFFFFFh
0x140055b86  movsxd  r8, ebp
0x140055b89  mov     [rsp+58h+cchCount2], ecx; cchCount2
0x140055b8d  lea     rax, ?s_astrServices@CMediaServer@@0PAPEBGA; ushort const * near * CMediaServer::s_astrServices
0x140055b94  mov     r9d, ecx; cchCount1
0x140055b97  mov     [rsp+58h+lpString2], rbx; lpString2
0x140055b9c  mov     r8, [rax+r8*8]; lpString1
0x140055ba0  lea     edx, [rcx+2]; dwCmpFlags
0x140055ba3  lea     ecx, [rdx+7Eh]; Locale
0x140055ba6  call    cs:__imp_CompareStringW
0x140055bac  cmp     eax, 2
0x140055baf  jz      short loc_140055BB5
0x140055bb1  inc     ebp
0x140055bb3  jmp     short loc_140055B7E
0x140055bb5  xor     ebx, ebx
0x140055bb7  mov     esi, ebp
0x140055bb9  mov     rcx, cs:WPP_GLOBAL_Control
0x140055bc0  cmp     rcx, r12
0x140055bc3  jz      short loc_140055BEE
0x140055bc5  test    byte ptr [rcx+1Ch], 2
0x140055bc9  jz      short loc_140055BEE
0x140055bcb  cmp     byte ptr [rcx+19h], 5
0x140055bcf  jb      short loc_140055BEE
0x140055bd1  mov     rcx, [rcx+10h]
0x140055bd5  lea     edx, [rbx+21h]
0x140055bd8  mov     r9d, ebp
0x140055bdb  lea     r8, WPP_02c6dcd2c5d83623206397dda38e97d9_Traceguids
0x140055be2  call    WPP_SF_d
0x140055be7  mov     rcx, cs:WPP_GLOBAL_Control
0x140055bee  cmp     ebp, 0FFFFFFFFh
0x140055bf1  jnz     short loc_140055C2A
0x140055bf3  jmp     short loc_140055BFC
0x140055bf5  mov     rcx, cs:WPP_GLOBAL_Control
0x140055bfc  cmp     rcx, r12
0x140055bff  jz      short loc_140055C25
0x140055c01  test    byte ptr [rcx+1Ch], 2
0x140055c05  jz      short loc_140055C25
0x140055c07  cmp     byte ptr [rcx+19h], 2
0x140055c0b  jb      short loc_140055C25
0x140055c0d  mov     rcx, [rcx+10h]
0x140055c11  lea     r8, WPP_02c6dcd2c5d83623206397dda38e97d9_Traceguids
0x140055c18  mov     edx, 22h ; '"'
0x140055c1d  mov     r9, r15
0x140055c20  call    WPP_SF_S
0x140055c25  mov     ebx, 80070057h
0x140055c2a  lea     rcx, [rsp+58h+arg_18]
0x140055c2f  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140055c34  test    ebx, ebx
0x140055c36  js      short loc_140055C97
0x140055c38  test    esi, esi
0x140055c3a  jz      loc_140055CD9
0x140055c40  sub     esi, 1
0x140055c43  jz      short loc_140055CA3
0x140055c45  cmp     esi, 1
0x140055c48  jnz     short loc_140055C97
0x140055c4a  mov     rcx, [r13+70h]
0x140055c4e  mov     [r14], rcx
0x140055c51  mov     rax, [rcx]
0x140055c54  mov     rax, [rax+8]
0x140055c58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140055c5d  mov     rax, cs:WPP_GLOBAL_Control
0x140055c64  cmp     rax, r12
0x140055c67  jz      loc_140055D76
0x140055c6d  test    byte ptr [rax+1Ch], 2
0x140055c71  jz      loc_140055D40
0x140055c77  cmp     byte ptr [rax+19h], 5
0x140055c7b  jb      loc_140055D40
0x140055c81  lea     edx, [rsi+24h]
0x140055c84  mov     r9, [r14]
0x140055c87  lea     r8, WPP_02c6dcd2c5d83623206397dda38e97d9_Traceguids
0x140055c8e  mov     rcx, [rax+10h]
0x140055c92  call    WPP_SF_q
0x140055c97  mov     rax, cs:WPP_GLOBAL_Control
0x140055c9e  jmp     loc_140055D40
0x140055ca3  mov     rcx, [r13+68h]
0x140055ca7  mov     [r14], rcx
0x140055caa  mov     rax, [rcx]
0x140055cad  mov     rax, [rax+8]
0x140055cb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140055cb6  mov     rax, cs:WPP_GLOBAL_Control
0x140055cbd  cmp     rax, r12
0x140055cc0  jz      loc_140055D76
0x140055cc6  test    byte ptr [rax+1Ch], 2
0x140055cca  jz      short loc_140055D40
0x140055ccc  cmp     byte ptr [rax+19h], 5
0x140055cd0  jb      short loc_140055D40
0x140055cd2  mov     edx, 24h ; '$'
0x140055cd7  jmp     short loc_140055C84
0x140055cd9  mov     rcx, [r13+60h]
0x140055cdd  mov     [r14], rcx
0x140055ce0  mov     rax, [rcx]
0x140055ce3  mov     rax, [rax+8]
0x140055ce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140055cec  mov     rax, cs:WPP_GLOBAL_Control
0x140055cf3  cmp     rax, r12
0x140055cf6  jz      short loc_140055D76
0x140055cf8  test    byte ptr [rax+1Ch], 2
0x140055cfc  jz      short loc_140055D40
0x140055cfe  cmp     byte ptr [rax+19h], 5
0x140055d02  jb      short loc_140055D40
0x140055d04  mov     edx, 23h ; '#'
0x140055d09  jmp     loc_140055C84
0x140055d0e  cmp     rax, r12
0x140055d11  jz      short loc_140055D3B
0x140055d13  test    byte ptr [rax+1Ch], 2
0x140055d17  jz      short loc_140055D3B
0x140055d19  cmp     byte ptr [rax+19h], 2
0x140055d1d  jb      short loc_140055D3B
0x140055d1f  mov     rcx, [rax+10h]
0x140055d23  lea     r8, WPP_02c6dcd2c5d83623206397dda38e97d9_Traceguids
0x140055d2a  mov     edx, 1Fh
0x140055d2f  call    WPP_SF_
0x140055d34  mov     rax, cs:WPP_GLOBAL_Control
0x140055d3b  mov     ebx, 80070057h
0x140055d40  cmp     rax, r12
0x140055d43  jz      short loc_140055D76
0x140055d45  test    byte ptr [rax+1Ch], 1
0x140055d49  jz      short loc_140055D76
0x140055d4b  movzx   ecx, byte ptr [rax+19h]
0x140055d4f  mov     edx, ebx
0x140055d51  sar     edx, 1Fh
0x140055d54  and     edx, 0FFFFFFFDh
0x140055d57  add     edx, 5
0x140055d5a  cmp     ecx, edx
0x140055d5c  jb      short loc_140055D76
0x140055d5e  mov     rcx, [rax+10h]
0x140055d62  lea     r8, WPP_02c6dcd2c5d83623206397dda38e97d9_Traceguids
0x140055d69  mov     edx, 26h ; '&'
0x140055d6e  mov     r9d, ebx
0x140055d71  call    WPP_SF_d
0x140055d76  mov     rbp, [rsp+58h+arg_8]
0x140055d7b  mov     eax, ebx
0x140055d7d  mov     rbx, [rsp+58h+arg_0]
0x140055d82  add     rsp, 30h
0x140055d86  pop     r15
0x140055d88  pop     r14
0x140055d8a  pop     r13
0x140055d8c  pop     r12
0x140055d8e  pop     rsi
0x140055d8f  retn
```
