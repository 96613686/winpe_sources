# ClCertValidateAce

- ea: `0x180039a34`
- end: `0x180039e1d`
- name: `ClCertValidateAce`
- size: `1001`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpValue@<rcx>, __int64, UCHAR pbOutput)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180039214`
- `0x1800395a4`

## callees

- `0x180020dc0`
- `0x1800214a4`
- `0x1800215e8`
- `0x1800268d8`
- `0x180037510`
- `0x18003756c`
- `0x180038020`
- `0x180038d98`
- `0x180039a34`
- `0x18003a68c`
- `0x18003ad98`
- `0x18003b158`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswxdigit` at `0x180039d57`
- `api-ms-win-crt-private-l1-1-0!_o_iswxdigit` at `0x180039d57`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180039a8c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180039a8c`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180039c4a`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180039c4a`
- `bcrypt!BCryptGetProperty` at `0x180039c7a`
- `bcrypt!BCryptGetProperty` at `0x180039c7a`

## string_xrefs

- `0x180039a79`: `System\CurrentControlSet\Services\LanmanServer\Certs`

## pseudocode

```c
__int64 __fastcall ClCertValidateAce(
        LPCWSTR lpValue,
        unsigned int a2,
        int a3,
        const WCHAR *a4,
        __int64 a5,
        BCRYPT_HANDLE *pbOutput)
{
  BCRYPT_HANDLE *v6; // r13
  __int64 v7; // rdi
  ULONG ValueW; // ebx
  BCRYPT_HANDLE v12; // rcx
  __int64 v14; // rsi
  int v15; // ecx
  unsigned __int64 v16; // r9
  _QWORD *v17; // rcx
  int v18; // edx
  unsigned int v19; // r9d
  __int64 v20; // r15
  int v21; // eax
  NTSTATUS v22; // ecx
  int v23; // edx
  NTSTATUS Property; // edi
  int v25; // r8d
  int v26; // edx
  int i; // edi
  ULONG pcbResult; // [rsp+40h] [rbp-28h] BYREF
  void *v29; // [rsp+48h] [rbp-20h]
  BCRYPT_HANDLE hObject[3]; // [rsp+50h] [rbp-18h] BYREF

  v6 = pbOutput;
  v7 = a3;
  v29 = 0;
  hObject[0] = 0;
  *pbOutput = 0;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Services\\LanmanServer\\Certs",
             lpValue,
             0x20u,
             0,
             0,
             0);
  if ( ValueW == 2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, WPP_053b19d310c5352633ee666709ba12ba_Traceguids, lpValue);
    }
  }
  else if ( ValueW )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        97,
        (unsigned int)WPP_053b19d310c5352633ee666709ba12ba_Traceguids,
        (_DWORD)lpValue,
        ValueW);
    }
  }
  else
  {
    v14 = -1;
    v15 = 0;
    if ( !a5 )
      goto LABEL_21;
    v16 = -1;
    do
      ++v16;
    while ( *(_WORD *)(a5 + 2 * v16) );
    if ( v16 <= 0x3E8 )
    {
LABEL_21:
      if ( a2 > 1 )
      {
        ValueW = 87;
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          v18 = 99;
          v19 = a2;
LABEL_26:
          WPP_SF_dS(v17[2], v18, (unsigned int)WPP_053b19d310c5352633ee666709ba12ba_Traceguids, v19, (__int64)lpValue);
        }
        goto LABEL_6;
      }
      while ( !v15 )
      {
        if ( (_DWORD)v7 == dword_18005C7A8 )
        {
          if ( (_DWORD)v7 != 1 )
          {
            hObject[0] = 0;
            LODWORD(pbOutput) = 0;
            pcbResult = 0;
            v20 = v7;
            v21 = ClCertDuplicateHashHandle(&xmmword_18005C830[v7], hObject);
            if ( v21 < 0 )
            {
              v22 = v21;
LABEL_33:
              ValueW = RtlNtStatusToDosErrorNoTeb(v22);
              goto LABEL_6;
            }
            Property = BCryptGetProperty(hObject[0], L"HashDigestLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0);
            if ( Property < 0 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) )
              {
                WPP_SF_dqS(*((_QWORD *)WPP_GLOBAL_Control + 2), v23, v25, Property, (char)hObject[0], (__int64)lpValue);
              }
              v22 = Property;
              goto LABEL_33;
            }
            v26 = 2 * (_DWORD)pbOutput;
            do
              ++v14;
            while ( a4[v14] );
            if ( v26 == v14 )
            {
              ClCertDestroyHashHandle(hObject[0]);
              for ( i = 0; a4[i]; ++i )
              {
                if ( !(unsigned int)_o_iswxdigit() )
                {
                  ValueW = 87;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
                  {
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, WPP_053b19d310c5352633ee666709ba12ba_Traceguids);
                  }
                  goto LABEL_6;
                }
              }
            }
            else
            {
              ValueW = 87;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) )
              {
                WPP_SF_SLIS(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v26,
                  v25,
                  (unsigned int)(&off_18004CD80)[v20],
                  2 * (_BYTE)pbOutput,
                  v14,
                  (__int64)lpValue);
              }
            }
            goto LABEL_6;
          }
LABEL_60:
          ValueW = ClCertGetCanonicalDistinguishedName(a4);
          if ( ValueW )
          {
            v12 = hObject[0];
          }
          else
          {
            v12 = 0;
            *v6 = hObject[0];
          }
          goto LABEL_7;
        }
        v15 = 1;
      }
      if ( (_DWORD)v7 != 1 )
      {
        ValueW = 87;
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          v18 = 100;
          v19 = v7;
          goto LABEL_26;
        }
        goto LABEL_6;
      }
      goto LABEL_60;
    }
    ValueW = 87;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_II(*((_QWORD *)WPP_GLOBAL_Control + 2));
    }
  }
LABEL_6:
  v12 = v29;
LABEL_7:
  ClCertLocalFree(v12);
  return ValueW;
}

```

## disassembly

```asm
0x180039a34  push    rbp
0x180039a36  push    rbx
0x180039a37  push    rsi
0x180039a38  push    rdi
0x180039a39  push    r12
0x180039a3b  push    r13
0x180039a3d  push    r14
0x180039a3f  push    r15
0x180039a41  mov     rbp, rsp
0x180039a44  sub     rsp, 68h
0x180039a48  mov     r13, [rbp+pbOutput]
0x180039a4c  xor     esi, esi
0x180039a4e  mov     eax, esi
0x180039a50  movsxd  rdi, r8d
0x180039a53  mov     r12, r9
0x180039a56  mov     [rsp+68h+pcbData], rsi; pcbData
0x180039a5b  mov     r15d, edx
0x180039a5e  mov     [rsp+68h+pvData], rsi; pvData
0x180039a63  mov     r14, rcx
0x180039a66  mov     [rbp+var_20], rax
0x180039a6a  mov     r8, rcx; lpValue
0x180039a6d  mov     [rbp+hObject], rax
0x180039a71  lea     r9d, [rsi+20h]; dwFlags
0x180039a75  mov     [r13+0], rsi
0x180039a79  lea     rdx, aSystemCurrentc_8; "System\\CurrentControlSet\\Services\\La"...
0x180039a80  mov     [rsp+68h+pdwType], rsi; pdwType
0x180039a85  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180039a8c  call    cs:__imp_RegGetValueW
0x180039a92  mov     ebx, eax
0x180039a94  cmp     eax, 2
0x180039a97  jnz     short loc_180039AED
0x180039a99  mov     rcx, cs:WPP_GLOBAL_Control
0x180039aa0  lea     rax, WPP_GLOBAL_Control
0x180039aa7  cmp     rcx, rax
0x180039aaa  jz      short loc_180039AD1
0x180039aac  test    dword ptr [rcx+1Ch], 800h
0x180039ab3  jz      short loc_180039AD1
0x180039ab5  cmp     byte ptr [rcx+19h], 1
0x180039ab9  jb      short loc_180039AD1
0x180039abb  mov     rcx, [rcx+10h]
0x180039abf  lea     edx, [rsi+60h]
0x180039ac2  mov     r9, r14
0x180039ac5  lea     r8, WPP_053b19d310c5352633ee666709ba12ba_Traceguids
0x180039acc  call    WPP_SF_S
0x180039ad1  mov     rcx, [rbp+var_20]
0x180039ad5  call    ClCertLocalFree
0x180039ada  mov     eax, ebx
0x180039adc  add     rsp, 68h
0x180039ae0  pop     r15
0x180039ae2  pop     r14
0x180039ae4  pop     r13
0x180039ae6  pop     r12
0x180039ae8  pop     rdi
0x180039ae9  pop     rsi
0x180039aea  pop     rbx
0x180039aeb  pop     rbp
0x180039aec  retn
0x180039aed  test    ebx, ebx
0x180039aef  jz      short loc_180039B31
0x180039af1  mov     rcx, cs:WPP_GLOBAL_Control
0x180039af8  lea     rax, WPP_GLOBAL_Control
0x180039aff  cmp     rcx, rax
0x180039b02  jz      short loc_180039AD1
0x180039b04  test    dword ptr [rcx+1Ch], 800h
0x180039b0b  jz      short loc_180039AD1
0x180039b0d  cmp     byte ptr [rcx+19h], 1
0x180039b11  jb      short loc_180039AD1
0x180039b13  mov     rcx, [rcx+10h]
0x180039b17  lea     r8, WPP_053b19d310c5352633ee666709ba12ba_Traceguids
0x180039b1e  mov     edx, 61h ; 'a'
0x180039b23  mov     dword ptr [rsp+68h+pdwType], ebx
0x180039b27  mov     r9, r14
0x180039b2a  call    WPP_SF_Sd
0x180039b2f  jmp     short loc_180039AD1
0x180039b31  mov     rax, [rbp+arg_20]
0x180039b35  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180039b39  xor     ecx, ecx
0x180039b3b  test    rax, rax
0x180039b3e  jz      short loc_180039B97
0x180039b40  mov     r9, rsi
0x180039b43  inc     r9
0x180039b46  cmp     [rax+r9*2], cx
0x180039b4b  jnz     short loc_180039B43
0x180039b4d  cmp     r9, 3E8h
0x180039b54  jbe     short loc_180039B97
0x180039b56  mov     ebx, 57h ; 'W'
0x180039b5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180039b62  lea     rax, WPP_GLOBAL_Control
0x180039b69  cmp     rcx, rax
0x180039b6c  jz      loc_180039AD1
0x180039b72  test    dword ptr [rcx+1Ch], 800h
0x180039b79  jz      loc_180039AD1
0x180039b7f  cmp     byte ptr [rcx+19h], 1
0x180039b83  jb      loc_180039AD1
0x180039b89  mov     rcx, [rcx+10h]
0x180039b8d  call    WPP_SF_II
0x180039b92  jmp     loc_180039AD1
0x180039b97  cmp     r15d, 1
0x180039b9b  jbe     short loc_180039BF0
0x180039b9d  mov     ebx, 57h ; 'W'
0x180039ba2  mov     rcx, cs:WPP_GLOBAL_Control
0x180039ba9  lea     rax, WPP_GLOBAL_Control
0x180039bb0  cmp     rcx, rax
0x180039bb3  jz      loc_180039AD1
0x180039bb9  test    dword ptr [rcx+1Ch], 800h
0x180039bc0  jz      loc_180039AD1
0x180039bc6  cmp     byte ptr [rcx+19h], 1
0x180039bca  jb      loc_180039AD1
0x180039bd0  lea     edx, [rbx+0Ch]
0x180039bd3  mov     r9d, r15d
0x180039bd6  mov     rcx, [rcx+10h]
0x180039bda  lea     r8, WPP_053b19d310c5352633ee666709ba12ba_Traceguids
0x180039be1  mov     [rsp+68h+pdwType], r14
0x180039be6  call    WPP_SF_dS
0x180039beb  jmp     loc_180039AD1
0x180039bf0  lea     rdx, __ImageBase
0x180039bf7  cmp     ecx, 1
0x180039bfa  jnb     loc_180039DB0
0x180039c00  mov     eax, ecx
0x180039c02  cmp     edi, rva dword_18005C7A8[rdx+rax*4]
0x180039c09  jz      short loc_180039C0F
0x180039c0b  inc     ecx
0x180039c0d  jmp     short loc_180039BF7
0x180039c0f  cmp     edi, 1
0x180039c12  jz      loc_180039DF3
0x180039c18  xor     r13d, r13d
0x180039c1b  lea     rax, xmmword_18005C830
0x180039c22  mov     rcx, rdi
0x180039c25  mov     [rbp+hObject], r13
0x180039c29  shl     rcx, 4
0x180039c2d  lea     rdx, [rbp+hObject]
0x180039c31  add     rcx, rax
0x180039c34  mov     dword ptr [rbp+pbOutput], r13d
0x180039c38  mov     [rbp+pcbResult], r13d
0x180039c3c  mov     r15, rdi
0x180039c3f  call    ClCertDuplicateHashHandle
0x180039c44  test    eax, eax
0x180039c46  jns     short loc_180039C57
0x180039c48  mov     ecx, eax; Status
0x180039c4a  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180039c50  mov     ebx, eax
0x180039c52  jmp     loc_180039AD1
0x180039c57  mov     rcx, [rbp+hObject]; hObject
0x180039c5b  lea     rax, [rbp+pcbResult]
0x180039c5f  mov     dword ptr [rsp+68h+pvData], r13d; dwFlags
0x180039c64  lea     r8, [rbp+pbOutput]; pbOutput
0x180039c68  mov     r9d, 4; cbOutput
0x180039c6e  mov     [rsp+68h+pdwType], rax; pcbResult
0x180039c73  lea     rdx, pszProperty; "HashDigestLength"
0x180039c7a  call    cs:__imp_BCryptGetProperty
0x180039c80  mov     edi, eax
0x180039c82  test    eax, eax
0x180039c84  jns     short loc_180039CC6
0x180039c86  mov     rcx, cs:WPP_GLOBAL_Control
0x180039c8d  lea     rax, WPP_GLOBAL_Control
0x180039c94  cmp     rcx, rax
0x180039c97  jz      short loc_180039CC2
0x180039c99  test    dword ptr [rcx+1Ch], 800h
0x180039ca0  jz      short loc_180039CC2
0x180039ca2  cmp     byte ptr [rcx+19h], 1
0x180039ca6  jb      short loc_180039CC2
0x180039ca8  mov     rax, [rbp+hObject]
0x180039cac  mov     r9d, edi
0x180039caf  mov     rcx, [rcx+10h]
0x180039cb3  mov     [rsp+68h+pvData], r14
0x180039cb8  mov     [rsp+68h+pdwType], rax
0x180039cbd  call    WPP_SF_dqS
0x180039cc2  mov     ecx, edi
0x180039cc4  jmp     short loc_180039C4A
0x180039cc6  mov     eax, dword ptr [rbp+pbOutput]
0x180039cc9  lea     edx, [rax+rax]
0x180039ccc  inc     rsi
0x180039ccf  cmp     [r12+rsi*2], r13w
0x180039cd4  jnz     short loc_180039CCC
0x180039cd6  mov     eax, edx
0x180039cd8  cmp     rax, rsi
0x180039cdb  jz      short loc_180039D3B
0x180039cdd  mov     ebx, 57h ; 'W'
0x180039ce2  mov     rcx, cs:WPP_GLOBAL_Control
0x180039ce9  lea     rax, WPP_GLOBAL_Control
0x180039cf0  cmp     rcx, rax
0x180039cf3  jz      loc_180039AD1
0x180039cf9  test    dword ptr [rcx+1Ch], 800h
0x180039d00  jz      loc_180039AD1
0x180039d06  cmp     byte ptr [rcx+19h], 1
0x180039d0a  jb      loc_180039AD1
0x180039d10  mov     rcx, [rcx+10h]
0x180039d14  lea     r9, __ImageBase
0x180039d1b  mov     r9, ds:rva off_18004CD80[r9+r15*8]; "SHA256" ...
0x180039d23  mov     [rsp+68h+pcbData], r14
0x180039d28  mov     [rsp+68h+pvData], rsi
0x180039d2d  mov     dword ptr [rsp+68h+pdwType], edx
0x180039d31  call    WPP_SF_SLIS
0x180039d36  jmp     loc_180039AD1
0x180039d3b  mov     rcx, [rbp+hObject]
0x180039d3f  call    ClCertDestroyHashHandle
0x180039d44  mov     edi, r13d
0x180039d47  mov     eax, edi
0x180039d49  movzx   ecx, word ptr [r12+rax*2]
0x180039d4e  test    cx, cx
0x180039d51  jz      loc_180039AD1
0x180039d57  call    cs:__imp__o_iswxdigit
0x180039d5d  test    eax, eax
0x180039d5f  jz      short loc_180039D65
0x180039d61  inc     edi
0x180039d63  jmp     short loc_180039D47
0x180039d65  mov     ebx, 57h ; 'W'
0x180039d6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180039d71  lea     rax, WPP_GLOBAL_Control
0x180039d78  cmp     rcx, rax
0x180039d7b  jz      loc_180039AD1
0x180039d81  test    dword ptr [rcx+1Ch], 800h
0x180039d88  jz      loc_180039AD1
0x180039d8e  cmp     byte ptr [rcx+19h], 1
0x180039d92  jb      loc_180039AD1
0x180039d98  mov     rcx, [rcx+10h]
0x180039d9c  lea     edx, [rbx+10h]
0x180039d9f  lea     r8, WPP_053b19d310c5352633ee666709ba12ba_Traceguids
0x180039da6  call    WPP_SF_
0x180039dab  jmp     loc_180039AD1
0x180039db0  cmp     edi, 1
0x180039db3  jz      short loc_180039DF3
0x180039db5  mov     ebx, 57h ; 'W'
0x180039dba  mov     rcx, cs:WPP_GLOBAL_Control
0x180039dc1  lea     rax, WPP_GLOBAL_Control
0x180039dc8  cmp     rcx, rax
0x180039dcb  jz      loc_180039AD1
0x180039dd1  test    dword ptr [rcx+1Ch], 800h
0x180039dd8  jz      loc_180039AD1
0x180039dde  cmp     byte ptr [rcx+19h], 1
0x180039de2  jb      loc_180039AD1
0x180039de8  lea     edx, [rbx+0Dh]
0x180039deb  mov     r9d, edi
0x180039dee  jmp     loc_180039BD6
0x180039df3  lea     rdx, [rbp+hObject]
0x180039df7  mov     rcx, r12; pszX500
0x180039dfa  call    ClCertGetCanonicalDistinguishedName
0x180039dff  mov     ebx, eax
0x180039e01  test    eax, eax
0x180039e03  jnz     short loc_180039E14
0x180039e05  mov     rax, [rbp+hObject]
0x180039e09  xor     ecx, ecx
0x180039e0b  mov     [r13+0], rax
0x180039e0f  jmp     loc_180039AD5
0x180039e14  mov     rcx, [rbp+hObject]
0x180039e18  jmp     loc_180039AD5
```
