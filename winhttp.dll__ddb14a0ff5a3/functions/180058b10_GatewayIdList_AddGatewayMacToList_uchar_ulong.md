# GatewayIdList::AddGatewayMacToList(uchar *,ulong)

- ea: `0x180058b10`
- end: `0x180058cb0`
- name: `?AddGatewayMacToList@GatewayIdList@@AEAAKPEAEK@Z`
- size: `416`
- prototype: `__int64 __fastcall(GatewayIdList *this, unsigned __int8 *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180058fc4`

## callees

- `0x180058b10`
- `0x180058cb8`
- `0x1800a2660`
- `0x1800d06a4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180058bd3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180058c39`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180058bd3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180058c39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180058b30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180058b30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180058c8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180058c8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058c07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058c07`

## pseudocode

```c
__int64 __fastcall GatewayIdList::AddGatewayMacToList(GatewayIdList *this, unsigned __int8 *a2, int a3)
{
  unsigned int v6; // ebx
  WCHAR *v7; // rax
  WCHAR *lpString2; // rsi
  __int64 v9; // rbx
  wchar_t *v10; // rbp
  unsigned int v11; // r14d
  __int64 v12; // r9
  unsigned int v13; // ebx
  __int64 i; // rbp
  __int64 v15; // rax
  LPVOID v17; // rax

  v6 = 6 * a3;
  v7 = (WCHAR *)CoTaskMemAlloc((unsigned int)(6 * a3));
  lpString2 = v7;
  if ( v7 )
  {
    memset_0(v7, 0, v6);
    v9 = 0;
    v10 = lpString2;
    v11 = a3 - 1;
    while ( 1 )
    {
      v12 = a2[v9];
      if ( (unsigned int)v9 >= v11 )
        break;
      if ( StringCchPrintfW(v10, 4u, L"%02x-", v12) < 0 )
        goto LABEL_20;
      v10 += 3;
      v9 = (unsigned int)(v9 + 1);
    }
    if ( StringCchPrintfW(v10, 3u, L"%02x", v12) < 0 )
    {
LABEL_20:
      v13 = 87;
    }
    else
    {
      v13 = 0;
      if ( (xmmword_180107A60 & 0x20) != 0 )
        WPP_SF_S(1029, 10, WPP_b5a40de8c1a73aed9fe132ba0faf3f6e_Traceguids, lpString2);
      if ( CompareStringW(0x7Fu, 1u, lpString2, -1, L"00-00-00-00-00-00", -1) == 2 )
      {
        *((_DWORD *)this + 1) = 0;
      }
      else
      {
        for ( i = 0; (unsigned int)i < *((_DWORD *)this + 4); i = (unsigned int)(i + 1) )
        {
          if ( CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(*((_QWORD *)this + 1) + 8 * i), -1, lpString2, -1) == 2 )
            goto LABEL_15;
        }
        v15 = *((unsigned int *)this + 5);
        if ( *((_DWORD *)this + 4) != (_DWORD)v15 )
          goto LABEL_13;
        if ( *((_DWORD *)this + 10) )
        {
          v17 = CoTaskMemRealloc(*((LPVOID *)this + 1), 8 * (v15 + *((unsigned int *)this + 10)));
          if ( v17 )
          {
            *((_DWORD *)this + 5) += *((_DWORD *)this + 10);
            *((_QWORD *)this + 1) = v17;
LABEL_13:
            *(_QWORD *)(*((_QWORD *)this + 1) + 8LL * (unsigned int)(*((_DWORD *)this + 4))++) = lpString2;
            return v13;
          }
          v13 = 8;
        }
        else
        {
          v13 = 1359;
        }
      }
    }
LABEL_15:
    CoTaskMemFree(lpString2);
  }
  else
  {
    return 8;
  }
  return v13;
}

```

## disassembly

```asm
0x180058b10  push    rbx
0x180058b12  push    rbp
0x180058b13  push    rsi
0x180058b14  push    rdi
0x180058b15  push    r14
0x180058b17  push    r15
0x180058b19  sub     rsp, 38h
0x180058b1d  lea     eax, [r8+r8*2]
0x180058b21  mov     rdi, rcx
0x180058b24  add     eax, eax
0x180058b26  mov     r14d, r8d
0x180058b29  mov     ecx, eax; cb
0x180058b2b  mov     r15, rdx
0x180058b2e  mov     ebx, eax
0x180058b30  call    cs:__imp_CoTaskMemAlloc
0x180058b36  mov     rsi, rax
0x180058b39  test    rax, rax
0x180058b3c  jz      loc_180058C48
0x180058b42  mov     r8d, ebx; Size
0x180058b45  xor     edx, edx; Val
0x180058b47  mov     rcx, rax; void *
0x180058b4a  call    memset_0
0x180058b4f  xor     ebx, ebx
0x180058b51  mov     rbp, rsi
0x180058b54  dec     r14d
0x180058b57  movzx   r9d, byte ptr [rbx+r15]
0x180058b5c  mov     rcx, rbp; pszDest
0x180058b5f  cmp     ebx, r14d
0x180058b62  jnb     short loc_180058B85
0x180058b64  lea     r8, a02x_0; "%02x-"
0x180058b6b  mov     edx, 4; cchDest
0x180058b70  call    StringCchPrintfW
0x180058b75  test    eax, eax
0x180058b77  js      loc_180058C4F
0x180058b7d  add     rbp, 6
0x180058b81  inc     ebx
0x180058b83  jmp     short loc_180058B57
0x180058b85  lea     r8, a02x; "%02x"
0x180058b8c  mov     edx, 3; cchDest
0x180058b91  call    StringCchPrintfW
0x180058b96  test    eax, eax
0x180058b98  js      loc_180058C4F
0x180058b9e  xor     ebx, ebx
0x180058ba0  test    byte ptr cs:xmmword_180107A60, 20h
0x180058ba7  jnz     loc_180058C56
0x180058bad  or      r14d, 0FFFFFFFFh
0x180058bb1  lea     rax, a000000000000; "00-00-00-00-00-00"
0x180058bb8  mov     [rsp+68h+cchCount2], r14d; cchCount2
0x180058bbd  mov     r9d, r14d; cchCount1
0x180058bc0  mov     r8, rsi; lpString1
0x180058bc3  mov     [rsp+68h+lpString2], rax; lpString2
0x180058bc8  lea     edx, [r14+2]; dwCmpFlags
0x180058bcc  lea     r15d, [rdx+7Eh]
0x180058bd0  mov     ecx, r15d; Locale
0x180058bd3  call    cs:__imp_CompareStringW
0x180058bd9  cmp     eax, 2
0x180058bdc  jz      short loc_180058C01
0x180058bde  xor     ebp, ebp
0x180058be0  cmp     ebp, [rdi+10h]
0x180058be3  jb      short loc_180058C1C
0x180058be5  mov     eax, [rdi+14h]
0x180058be8  cmp     [rdi+10h], eax
0x180058beb  jz      loc_180058C74
0x180058bf1  mov     edx, [rdi+10h]
0x180058bf4  mov     rcx, [rdi+8]
0x180058bf8  mov     [rcx+rdx*8], rsi
0x180058bfc  inc     dword ptr [rdi+10h]
0x180058bff  jmp     short loc_180058C0D
0x180058c01  mov     [rdi+4], ebx
0x180058c04  mov     rcx, rsi; pv
0x180058c07  call    cs:__imp_CoTaskMemFree
0x180058c0d  mov     eax, ebx
0x180058c0f  add     rsp, 38h
0x180058c13  pop     r15
0x180058c15  pop     r14
0x180058c17  pop     rdi
0x180058c18  pop     rsi
0x180058c19  pop     rbp
0x180058c1a  pop     rbx
0x180058c1b  retn
0x180058c1c  mov     r8, [rdi+8]
0x180058c20  mov     r9d, r14d; cchCount1
0x180058c23  mov     [rsp+68h+cchCount2], r14d; cchCount2
0x180058c28  mov     edx, 1; dwCmpFlags
0x180058c2d  mov     ecx, r15d; Locale
0x180058c30  mov     [rsp+68h+lpString2], rsi; lpString2
0x180058c35  mov     r8, [r8+rbp*8]; lpString1
0x180058c39  call    cs:__imp_CompareStringW
0x180058c3f  cmp     eax, 2
0x180058c42  jz      short loc_180058C04
0x180058c44  inc     ebp
0x180058c46  jmp     short loc_180058BE0
0x180058c48  mov     ebx, 8
0x180058c4d  jmp     short loc_180058C0D
0x180058c4f  mov     ebx, 57h ; 'W'
0x180058c54  jmp     short loc_180058C04
0x180058c56  mov     edx, 0Ah
0x180058c5b  lea     r8, WPP_b5a40de8c1a73aed9fe132ba0faf3f6e_Traceguids
0x180058c62  mov     ecx, 405h
0x180058c67  mov     r9, rsi
0x180058c6a  call    WPP_SF_S
0x180058c6f  jmp     loc_180058BAD
0x180058c74  cmp     [rdi+28h], ebx
0x180058c77  jnz     short loc_180058C80
0x180058c79  mov     ebx, 54Fh
0x180058c7e  jmp     short loc_180058C04
0x180058c80  mov     edx, [rdi+28h]
0x180058c83  mov     rcx, [rdi+8]; pv
0x180058c87  add     rdx, rax
0x180058c8a  shl     rdx, 3; cb
0x180058c8e  call    cs:__imp_CoTaskMemRealloc
0x180058c94  test    rax, rax
0x180058c97  jnz     short loc_180058CA1
0x180058c99  lea     ebx, [rax+8]
0x180058c9c  jmp     loc_180058C04
0x180058ca1  mov     ecx, [rdi+28h]
0x180058ca4  add     [rdi+14h], ecx
0x180058ca7  mov     [rdi+8], rax
0x180058cab  jmp     loc_180058BF1
```
