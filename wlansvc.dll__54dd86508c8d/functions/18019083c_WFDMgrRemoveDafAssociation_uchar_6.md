# WFDMgrRemoveDafAssociation(uchar (*)[6])

- ea: `0x18019083c`
- end: `0x180190b97`
- name: `?WFDMgrRemoveDafAssociation@@YAKPEAY05E@Z`
- size: `859`
- prototype: `unsigned int __fastcall(unsigned __int8 (*)[6])`
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x1801670f0`
- `0x1801906c0`
- `0x180190bc0`
- `0x180197b2c`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x18002f450`
- `0x1800b2080`
- `0x180106340`
- `0x180107330`
- `0x18019083c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180190af7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180190af7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180190918`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180190918`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180190928`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180190928`
- `deviceassociation!DafCreateAssociationContext` at `0x180190a98`
- `deviceassociation!DafCreateAssociationContext` at `0x180190a98`
- `deviceassociation!DafCloseAssociationContext` at `0x180190b44`
- `deviceassociation!DafCloseAssociationContext` at `0x180190b44`
- `deviceassociation!DafStartRemoveAssociation` at `0x180190ae5`
- `deviceassociation!DafStartRemoveAssociation` at `0x180190ae5`

## pseudocode

```c
__int64 __fastcall WFDMgrRemoveDafAssociation(unsigned __int8 (*a1)[6])
{
  PVOID *v2; // rcx
  int v3; // ebx
  DWORD LastError; // eax
  __int64 v5; // rdx
  __int64 v6; // rdi
  __int64 v8; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE hHandle[2]; // [rsp+40h] [rbp-C0h] BYREF
  int v10[3]; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v11; // [rsp+5Ch] [rbp-A4h]

  memset_0(v10, 0, 0x218u);
  v8 = 0;
  *(_OWORD *)hHandle = 0;
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 1720, &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    if ( v2 != &WPP_GLOBAL_Control && *((_BYTE *)v2 + 105) && (*((_BYTE *)v2 + 108) & 1) != 0 )
    {
      WPP_SF_(v2[12], 1721, &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids);
      v2 = (PVOID *)WPP_GLOBAL_Control;
    }
    v3 = 87;
    goto LABEL_48;
  }
  hHandle[0] = CreateEventW(0, 0, 0, 0);
  if ( !hHandle[0] )
  {
    LastError = GetLastError();
    v3 = LastError;
    v2 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || !*((_BYTE *)WPP_GLOBAL_Control + 105)
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
    {
      goto LABEL_48;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 1722, &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids, LastError);
    goto LABEL_47;
  }
  v10[2] = *(_DWORD *)a1;
  v11 = *(_WORD *)&(*a1)[4];
  v10[0] = 5;
  v10[1] = 1;
  v3 = WfdDafObjectStringEncode((int)v10);
  if ( v3 < 0 )
  {
    v2 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      v5 = 1723;
LABEL_21:
      WPP_SF_d(v2[12], v5, &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids, (unsigned int)v3);
      v2 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_22;
    }
    goto LABEL_22;
  }
  v6 = AllocWLMem(2u);
  if ( v6 )
  {
    v3 = WfdDafObjectStringEncode((int)v10);
    if ( v3 >= 0 )
    {
      v3 = DafCreateAssociationContext(v6, 0, 0, 0, &v8);
      if ( v3 >= 0 )
      {
        v3 = 0;
        if ( (int)DafStartRemoveAssociation(v8, WFDMgrRemoveDafAssociationCallback, hHandle) >= 0 )
          WaitForSingleObject(hHandle[0], 0xFFFFFFFF);
        if ( SLODWORD(hHandle[1]) < 0 )
        {
          v2 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || *((_BYTE *)WPP_GLOBAL_Control + 105) < 2u
            || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
          {
            goto LABEL_48;
          }
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            1727,
            &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids,
            LODWORD(hHandle[1]));
        }
LABEL_47:
        v2 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_48;
      }
      v2 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !*((_BYTE *)WPP_GLOBAL_Control + 105)
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      {
        goto LABEL_22;
      }
      v5 = 1726;
      goto LABEL_21;
    }
    v2 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      v5 = 1725;
      goto LABEL_21;
    }
LABEL_22:
    if ( (v3 & 0x1FFF0000) == 0x70000 )
      v3 = (unsigned __int16)v3;
    goto LABEL_48;
  }
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105)
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 1724, &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  v3 = 14;
LABEL_48:
  if ( v8 )
  {
    DafCloseAssociationContext(v8);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && *((_BYTE *)v2 + 105) >= 4u && (*((_BYTE *)v2 + 108) & 1) != 0 )
    WPP_SF_d(v2[12], 1728, &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids, (unsigned int)v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18019083c  push    rbp
0x18019083e  push    rbx
0x18019083f  push    rsi
0x180190840  push    rdi
0x180190841  push    r14
0x180190843  push    r15
0x180190845  lea     rbp, [rsp-188h]
0x18019084d  sub     rsp, 288h
0x180190854  mov     rax, cs:__security_cookie
0x18019085b  xor     rax, rsp
0x18019085e  mov     [rbp+1B0h+var_40], rax
0x180190865  mov     rbx, rcx
0x180190868  mov     [rsp+2B0h+var_280], 0
0x180190870  lea     rcx, [rsp+2B0h+var_260]; void *
0x180190875  xor     edx, edx; Val
0x180190877  mov     r8d, 218h; Size
0x18019087d  call    memset_0
0x180190882  xorps   xmm0, xmm0
0x180190885  mov     [rsp+2B0h+var_278], 0
0x18019088e  movups  xmmword ptr [rsp+2B0h+hHandle], xmm0
0x180190893  mov     rcx, cs:WPP_GLOBAL_Control
0x18019089a  lea     r14, WPP_GLOBAL_Control
0x1801908a1  lea     r15, WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids
0x1801908a8  mov     esi, 1
0x1801908ad  cmp     rcx, r14
0x1801908b0  jz      short loc_1801908D6
0x1801908b2  cmp     byte ptr [rcx+69h], 4
0x1801908b6  jb      short loc_1801908D6
0x1801908b8  test    [rcx+6Ch], sil
0x1801908bc  jz      short loc_1801908D6
0x1801908be  mov     rcx, [rcx+60h]
0x1801908c2  mov     edx, 6B8h
0x1801908c7  mov     r8, r15
0x1801908ca  call    WPP_SF_
0x1801908cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1801908d6  test    rbx, rbx
0x1801908d9  jnz     short loc_18019090E
0x1801908db  cmp     rcx, r14
0x1801908de  jz      short loc_180190904
0x1801908e0  cmp     [rcx+69h], sil
0x1801908e4  jb      short loc_180190904
0x1801908e6  test    [rcx+6Ch], sil
0x1801908ea  jz      short loc_180190904
0x1801908ec  mov     rcx, [rcx+60h]
0x1801908f0  mov     edx, 6B9h
0x1801908f5  mov     r8, r15
0x1801908f8  call    WPP_SF_
0x1801908fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180190904  mov     ebx, 57h ; 'W'
0x180190909  jmp     loc_180190B37
0x18019090e  xor     r9d, r9d; lpName
0x180190911  xor     r8d, r8d; bInitialState
0x180190914  xor     edx, edx; bManualReset
0x180190916  xor     ecx, ecx; lpEventAttributes
0x180190918  call    cs:__imp_CreateEventW
0x18019091e  mov     [rsp+2B0h+hHandle], rax
0x180190923  test    rax, rax
0x180190926  jnz     short loc_18019096D
0x180190928  call    cs:__imp_GetLastError
0x18019092e  mov     ebx, eax
0x180190930  mov     rcx, cs:WPP_GLOBAL_Control
0x180190937  cmp     rcx, r14
0x18019093a  jz      loc_180190B37
0x180190940  cmp     [rcx+69h], sil
0x180190944  jb      loc_180190B37
0x18019094a  test    [rcx+6Ch], sil
0x18019094e  jz      loc_180190B37
0x180190954  mov     rcx, [rcx+60h]
0x180190958  mov     edx, 6BAh
0x18019095d  mov     r9d, eax
0x180190960  mov     r8, r15
0x180190963  call    WPP_SF_d
0x180190968  jmp     loc_180190B30
0x18019096d  mov     eax, [rbx]
0x18019096f  lea     r8, [rsp+2B0h+var_280]
0x180190974  mov     [rsp+2B0h+var_258], eax
0x180190978  lea     rcx, [rsp+2B0h+var_260]; int
0x18019097d  movzx   eax, word ptr [rbx+4]
0x180190981  xor     r9d, r9d
0x180190984  mov     [rsp+2B0h+var_254], ax
0x180190989  mov     [rsp+2B0h+var_260], 5
0x180190991  mov     [rsp+2B0h+var_25C], esi
0x180190995  call    WfdDafObjectStringEncode
0x18019099a  mov     ebx, eax
0x18019099c  test    eax, eax
0x18019099e  jns     short loc_1801909ED
0x1801909a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1801909a7  cmp     rcx, r14
0x1801909aa  jz      short loc_1801909D3
0x1801909ac  cmp     [rcx+69h], sil
0x1801909b0  jb      short loc_1801909D3
0x1801909b2  test    [rcx+6Ch], sil
0x1801909b6  jz      short loc_1801909D3
0x1801909b8  mov     edx, 6BBh
0x1801909bd  mov     rcx, [rcx+60h]
0x1801909c1  mov     r9d, ebx
0x1801909c4  mov     r8, r15
0x1801909c7  call    WPP_SF_d
0x1801909cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1801909d3  mov     eax, ebx
0x1801909d5  and     eax, 1FFF0000h
0x1801909da  cmp     eax, 70000h
0x1801909df  jnz     loc_180190B37
0x1801909e5  movzx   ebx, bx
0x1801909e8  jmp     loc_180190B37
0x1801909ed  mov     ecx, [rsp+2B0h+var_280]
0x1801909f1  inc     ecx
0x1801909f3  add     rcx, rcx; dwBytes
0x1801909f6  call    AllocWLMem
0x1801909fb  mov     rdi, rax
0x1801909fe  test    rax, rax
0x180190a01  jnz     short loc_180190A3D
0x180190a03  mov     rcx, cs:WPP_GLOBAL_Control
0x180190a0a  cmp     rcx, r14
0x180190a0d  jz      short loc_180190A33
0x180190a0f  cmp     [rcx+69h], sil
0x180190a13  jb      short loc_180190A33
0x180190a15  test    [rcx+6Ch], sil
0x180190a19  jz      short loc_180190A33
0x180190a1b  mov     rcx, [rcx+60h]
0x180190a1f  mov     edx, 6BCh
0x180190a24  mov     r8, r15
0x180190a27  call    WPP_SF_
0x180190a2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180190a33  mov     ebx, 0Eh
0x180190a38  jmp     loc_180190B37
0x180190a3d  mov     r9, rdi
0x180190a40  lea     r8, [rsp+2B0h+var_280]
0x180190a45  lea     rcx, [rsp+2B0h+var_260]; int
0x180190a4a  call    WfdDafObjectStringEncode
0x180190a4f  mov     ebx, eax
0x180190a51  test    eax, eax
0x180190a53  jns     short loc_180190A83
0x180190a55  mov     rcx, cs:WPP_GLOBAL_Control
0x180190a5c  cmp     rcx, r14
0x180190a5f  jz      loc_1801909D3
0x180190a65  cmp     [rcx+69h], sil
0x180190a69  jb      loc_1801909D3
0x180190a6f  test    [rcx+6Ch], sil
0x180190a73  jz      loc_1801909D3
0x180190a79  mov     edx, 6BDh
0x180190a7e  jmp     loc_1801909BD
0x180190a83  lea     rax, [rsp+2B0h+var_278]
0x180190a88  xor     r9d, r9d
0x180190a8b  xor     r8d, r8d
0x180190a8e  mov     [rsp+2B0h+var_290], rax
0x180190a93  xor     edx, edx
0x180190a95  mov     rcx, rdi
0x180190a98  call    cs:__imp_DafCreateAssociationContext
0x180190a9e  mov     ebx, eax
0x180190aa0  test    eax, eax
0x180190aa2  jns     short loc_180190AD2
0x180190aa4  mov     rcx, cs:WPP_GLOBAL_Control
0x180190aab  cmp     rcx, r14
0x180190aae  jz      loc_1801909D3
0x180190ab4  cmp     [rcx+69h], sil
0x180190ab8  jb      loc_1801909D3
0x180190abe  test    [rcx+6Ch], sil
0x180190ac2  jz      loc_1801909D3
0x180190ac8  mov     edx, 6BEh
0x180190acd  jmp     loc_1801909BD
0x180190ad2  mov     rcx, [rsp+2B0h+var_278]
0x180190ad7  lea     r8, [rsp+2B0h+hHandle]
0x180190adc  lea     rdx, ?WFDMgrRemoveDafAssociationCallback@@YAXPEAXJ@Z; WFDMgrRemoveDafAssociationCallback(void *,long)
0x180190ae3  xor     ebx, ebx
0x180190ae5  call    cs:__imp_DafStartRemoveAssociation
0x180190aeb  test    eax, eax
0x180190aed  js      short loc_180190AFD
0x180190aef  mov     rcx, [rsp+2B0h+hHandle]; hHandle
0x180190af4  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180190af7  call    cs:__imp_WaitForSingleObject
0x180190afd  mov     r9d, dword ptr [rsp+2B0h+hHandle+8]
0x180190b02  test    r9d, r9d
0x180190b05  jns     short loc_180190B30
0x180190b07  mov     rcx, cs:WPP_GLOBAL_Control
0x180190b0e  cmp     rcx, r14
0x180190b11  jz      short loc_180190B37
0x180190b13  cmp     byte ptr [rcx+69h], 2
0x180190b17  jb      short loc_180190B37
0x180190b19  test    [rcx+6Ch], sil
0x180190b1d  jz      short loc_180190B37
0x180190b1f  mov     rcx, [rcx+60h]
0x180190b23  mov     edx, 6BFh
0x180190b28  mov     r8, r15
0x180190b2b  call    WPP_SF_d
0x180190b30  mov     rcx, cs:WPP_GLOBAL_Control
0x180190b37  mov     rax, [rsp+2B0h+var_278]
0x180190b3c  test    rax, rax
0x180190b3f  jz      short loc_180190B51
0x180190b41  mov     rcx, rax
0x180190b44  call    cs:__imp_DafCloseAssociationContext
0x180190b4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180190b51  cmp     rcx, r14
0x180190b54  jz      short loc_180190B76
0x180190b56  cmp     byte ptr [rcx+69h], 4
0x180190b5a  jb      short loc_180190B76
0x180190b5c  test    [rcx+6Ch], sil
0x180190b60  jz      short loc_180190B76
0x180190b62  mov     rcx, [rcx+60h]
0x180190b66  mov     edx, 6C0h
0x180190b6b  mov     r9d, ebx
0x180190b6e  mov     r8, r15
0x180190b71  call    WPP_SF_d
0x180190b76  mov     eax, ebx
0x180190b78  mov     rcx, [rbp+1B0h+var_40]
0x180190b7f  xor     rcx, rsp; StackCookie
0x180190b82  call    __security_check_cookie
0x180190b87  add     rsp, 288h
0x180190b8e  pop     r15
0x180190b90  pop     r14
0x180190b92  pop     rdi
0x180190b93  pop     rsi
0x180190b94  pop     rbx
0x180190b95  pop     rbp
0x180190b96  retn
```
