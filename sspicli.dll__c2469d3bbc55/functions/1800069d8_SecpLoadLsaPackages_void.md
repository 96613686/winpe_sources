# SecpLoadLsaPackages(void)

- ea: `0x1800069d8`
- end: `0x180006ea3`
- name: `?SecpLoadLsaPackages@@YAJXZ`
- size: `1227`
- prototype: `__int64(void)`
- caller_count: `7`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003ee0`
- `0x1800049c0`
- `0x180005400`
- `0x180005860`
- `0x1800061a0`
- `0x180007200`
- `0x180009c90`

## callees

- `0x1800069d8`
- `0x1800079f8`
- `0x180007c90`
- `0x180007d30`
- `0x1800084f0`
- `0x180009744`
- `0x18000d2b0`
- `0x18000e084`
- `0x18000ee2c`
- `0x180013e40`
- `0x18001d690`
- `0x180022047`
- `0x18002205f`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!_wcsicmp` at `0x180006dce`
- `api-ms-win-core-crt-l1-1-0!_wcsicmp` at `0x180006dce`
- `ntdll!RtlReleaseResource` at `0x180006dfd`
- `ntdll!RtlReleaseResource` at `0x180006dfd`
- `ntdll!RtlAcquireResourceShared` at `0x180006da3`
- `ntdll!RtlAcquireResourceShared` at `0x180006da3`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x180006b45`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x180006be7`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x180006b45`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x180006be7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006a65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006a6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006ce5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006e0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006a65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006a6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006ce5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006e0f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006a2b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006a3b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006ae3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006b94`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006e4f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006a2b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006a3b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006ae3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006b94`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006e4f`

## pseudocode

```c
NTSTATUS SecpLoadLsaPackages(void)
{
  NTSTATUS result; // eax
  unsigned int v1; // r12d
  char *v2; // rbx
  struct _UNICODE_STRING *v3; // rdi
  int v4; // edx
  int v5; // r8d
  struct _UNICODE_STRING *v6; // rcx
  WCHAR *v7; // r14
  _WORD *v8; // r15
  size_t v9; // rsi
  HLOCAL v10; // rax
  _WORD *v11; // r15
  __int64 v12; // rsi
  WCHAR *v13; // r13
  HLOCAL v14; // rax
  unsigned int *v15; // rsi
  int Length; // eax
  __int64 v17; // rax
  int v18; // r15d
  wchar_t *v19; // r13
  __int64 v20; // rdx
  int v21; // r8d
  __int64 v22; // rdx
  __int64 v23; // r8
  unsigned int v24; // r8d
  __int64 v25; // rsi
  __int64 v26; // rdx
  int v27; // eax
  struct _UNICODE_STRING *v28; // rsi
  size_t v29; // r15
  HLOCAL v30; // rax
  struct _UNICODE_STRING v31; // [rsp+30h] [rbp-99h] BYREF
  _STRING DestinationString; // [rsp+40h] [rbp-89h] BYREF
  USHORT v33; // [rsp+50h] [rbp-79h] BYREF
  int v34; // [rsp+52h] [rbp-77h]
  USHORT v35; // [rsp+56h] [rbp-73h]
  PVOID Buffer; // [rsp+58h] [rbp-71h]
  unsigned __int16 v37; // [rsp+60h] [rbp-69h]
  int v38; // [rsp+62h] [rbp-67h]
  USHORT v39; // [rsp+66h] [rbp-63h]
  void *Src; // [rsp+68h] [rbp-61h]
  USHORT v41; // [rsp+70h] [rbp-59h]
  int v42; // [rsp+72h] [rbp-57h]
  USHORT v43; // [rsp+76h] [rbp-53h]
  wchar_t *String1; // [rsp+78h] [rbp-51h]
  int v45; // [rsp+80h] [rbp-49h]
  int v46; // [rsp+84h] [rbp-45h]
  int v47; // [rsp+88h] [rbp-41h]
  __int16 v48; // [rsp+8Ch] [rbp-3Dh]
  __int16 v49; // [rsp+90h] [rbp-39h]
  int v50; // [rsp+94h] [rbp-35h]
  unsigned int v51; // [rsp+98h] [rbp-31h]
  char v52[132]; // [rsp+9Ch] [rbp-2Dh] BYREF
  struct _RTL_RESOURCE *Resource; // [rsp+130h] [rbp+67h]

  memset_0(&v33, 0, 0x90u);
  DestinationString = 0;
  result = IsOkayToExec(0);
  if ( !result )
  {
    v1 = 0;
    if ( SecLsaPackageCount )
    {
      while ( 1 )
      {
        v2 = (char *)LocalAlloc(0x40u, 0xF8u);
        v3 = (struct _UNICODE_STRING *)LocalAlloc(0, 0x38u);
        if ( !v3 )
          break;
        if ( !v2 )
          goto LABEL_7;
        if ( (int)SecpGetBinding(v1, &v33) < 0 )
        {
          LocalFree(v2);
          goto LABEL_7;
        }
        v7 = (WCHAR *)Buffer;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_dS(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, v5, v1, (__int64)Buffer);
        v8 = v2 + 96;
        v9 = v33;
        *(_DWORD *)&v31.MaximumLength = v34;
        v31.Length = v33;
        *(&v31.MaximumLength + 2) = v35;
        v31.Buffer = v7;
        v10 = LocalAlloc(0, v33 + 2LL);
        *((_QWORD *)v2 + 13) = v10;
        if ( !v10 )
          goto LABEL_15;
        *((_WORD *)v2 + 49) = v9 + 2;
        if ( (unsigned __int16)(v9 + 2) < (unsigned __int16)v9 )
          goto LABEL_15;
        *v8 = v9;
        memcpy_0(v10, v7, v9);
        *(_WORD *)(*((_QWORD *)v2 + 13) + 2 * ((unsigned __int64)(unsigned __int16)*v8 >> 1)) = 0;
        if ( RtlUnicodeStringToAnsiString(&DestinationString, (PCUNICODE_STRING)v2 + 6, 1u) < 0 )
          goto LABEL_15;
        v11 = v2 + 112;
        v12 = v37;
        v13 = (WCHAR *)Src;
        *((_QWORD *)v2 + 16) = DestinationString.Buffer;
        v31.Length = v12;
        *((_DWORD *)v2 + 34) = DestinationString.Length + 1;
        *(_DWORD *)&v31.MaximumLength = v38;
        *(&v31.MaximumLength + 2) = v39;
        v31.Buffer = v13;
        v14 = LocalAlloc(0, v12 + 2);
        *((_QWORD *)v2 + 15) = v14;
        if ( !v14
          || (*((_WORD *)v2 + 57) = v12 + 2, (unsigned __int16)(v12 + 2) < (unsigned __int16)v12)
          || (*v11 = v12,
              memcpy_0(v14, v13, (unsigned int)v12),
              *(_WORD *)(*((_QWORD *)v2 + 15) + 2 * ((unsigned __int64)(unsigned __int16)*v11 >> 1)) = 0,
              RtlUnicodeStringToAnsiString(&DestinationString, (PCUNICODE_STRING)v2 + 7, 1u) < 0) )
        {
LABEL_15:
          SecpFreePackage(v2, 0);
          LsaFreeReturnBuffer(v7);
LABEL_7:
          v6 = v3;
LABEL_8:
          LocalFree(v6);
          goto LABEL_9;
        }
        v15 = (unsigned int *)(v2 + 216);
        *((_QWORD *)v2 + 18) = DestinationString.Buffer;
        Length = DestinationString.Length;
        *((_DWORD *)v2 + 9) |= 4u;
        *((_DWORD *)v2 + 38) = Length + 1;
        *((_DWORD *)v2 + 8) = v45;
        *((_DWORD *)v2 + 20) = v46;
        *((_WORD *)v2 + 42) = v49;
        *((_WORD *)v2 + 43) = v48;
        *((_DWORD *)v2 + 23) = v50;
        *((_DWORD *)v2 + 4) = 50;
        *((_QWORD *)v2 + 26) = v2 + 216;
        *((_QWORD *)v2 + 30) = v2 + 232;
        *((_QWORD *)v2 + 29) = v2 + 232;
        v17 = v51;
        if ( v51 )
        {
          *v15 = v51;
          v29 = 4 * v17;
          v30 = LocalAlloc(0, 4 * v17);
          *((_QWORD *)v2 + 28) = v30;
          if ( v30 )
            memcpy_0(v30, v52, v29);
          else
            *v15 = 0;
        }
        v18 = v47 & 1;
        if ( (v47 & 1) != 0 )
        {
          LocalFree(v3);
          ++dword_18003FE90;
          v3 = (struct _UNICODE_STRING *)&SecpBuiltinBinding;
LABEL_25:
          *((_DWORD *)v2 + 9) |= 0x11u;
          *((_QWORD *)v2 + 3) = v1;
          *((_QWORD *)v2 + 5) = v1;
          *((_QWORD *)v2 + 6) = v1;
          *((_QWORD *)v2 + 7) = v3;
          SecpAddDllPackage((struct _DLL_SECURITY_PACKAGE *)v2);
          LsaFreeReturnBuffer(v7);
          SecpDerefDll((HLOCAL *)v3);
          if ( v18 )
          {
            SecpSnapNewDll((struct _DLL_SECURITY_PACKAGE *)v2, v20, v21);
            *((_DWORD *)v2 + 9) &= ~4u;
          }
          goto LABEL_9;
        }
        v19 = String1;
        if ( *((_DWORD *)v2 + 8) == v18 )
          goto LABEL_23;
        v31.Length = v41;
        *(_DWORD *)&v31.MaximumLength = v42;
        *(&v31.MaximumLength + 2) = v43;
        v31.Buffer = String1;
        Resource = (struct _RTL_RESOURCE *)&SecPackageListLock[12
                                                             * ((unsigned int)(SecPackageListLockCount - 1)
                                                              & (unsigned __int64)NtCurrentTeb()->CurrentIdealProcessor.Reserved)];
        RtlAcquireResourceShared(Resource, 1u);
        v24 = SecPackageDllCount;
        v25 = 0;
        if ( !SecPackageDllCount )
          goto LABEL_38;
        do
        {
          v26 = *((_QWORD *)SecPackageDllList + v25);
          if ( v26 )
          {
            v27 = _wcsicmp(v19, *(const wchar_t **)(v26 + 24));
            v24 = SecPackageDllCount;
            if ( !v27 )
              break;
          }
          v25 = (unsigned int)(v25 + 1);
        }
        while ( (unsigned int)v25 < v24 );
        if ( (unsigned int)v25 < v24 )
        {
          _mm_lfence();
          v28 = (struct _UNICODE_STRING *)*((_QWORD *)SecPackageDllList + v25);
        }
        else
        {
LABEL_38:
          v28 = 0;
        }
        RtlReleaseResource(Resource);
        if ( !v28 )
        {
LABEL_23:
          *v3 = 0;
          v3[1] = 0;
          v3[2] = 0;
          *(_QWORD *)&v3[3].Length = 0;
        }
        else
        {
          LocalFree(v3);
          v3 = v28;
        }
        ++*(_DWORD *)&v3[2].Length;
        if ( v3[1].Buffer )
          goto LABEL_25;
        v31.Length = v41;
        *(_DWORD *)&v31.MaximumLength = v42;
        *(&v31.MaximumLength + 2) = v43;
        *(_DWORD *)&v3->Length = 1;
        v31.Buffer = v19;
        if ( (unsigned int)SecpDuplicateString(v3 + 1, &v31) )
        {
          if ( (unsigned int)SecpAddDll((struct _SECP_DLL_BINDING *)v3, v22, v23) )
            goto LABEL_25;
        }
        SecpFreePackage(v2, 0);
        LsaFreeReturnBuffer(v7);
        SecpDerefDll((HLOCAL *)v3);
LABEL_9:
        if ( ++v1 >= SecLsaPackageCount )
          goto LABEL_10;
      }
      if ( !v2 )
        goto LABEL_9;
      v6 = (struct _UNICODE_STRING *)v2;
      goto LABEL_8;
    }
LABEL_10:
    SecPackageLsaLoaded = 1;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800069d8  push    rbp
0x1800069da  push    rbx
0x1800069db  push    rsi
0x1800069dc  push    rdi
0x1800069dd  push    r12
0x1800069df  push    r13
0x1800069e1  push    r14
0x1800069e3  push    r15
0x1800069e5  lea     rbp, [rsp-1Fh]
0x1800069ea  sub     rsp, 0E8h
0x1800069f1  xor     edx, edx; Val
0x1800069f3  lea     rcx, [rbp+57h+var_D0]; void *
0x1800069f7  mov     r8d, 90h; Size
0x1800069fd  call    memset_0
0x180006a02  xorps   xmm0, xmm0
0x180006a05  xor     ecx, ecx
0x180006a07  movups  xmmword ptr [rsp+120h+DestinationString.Length], xmm0
0x180006a0c  call    IsOkayToExec
0x180006a11  test    eax, eax
0x180006a13  jnz     short loc_180006A8C
0x180006a15  xor     r12d, r12d
0x180006a18  cmp     cs:SecLsaPackageCount, r12d
0x180006a1f  jbe     short loc_180006A80
0x180006a21  mov     edx, 0F8h; uBytes
0x180006a26  mov     ecx, 40h ; '@'; uFlags
0x180006a2b  call    cs:__imp_LocalAlloc
0x180006a31  mov     edx, 38h ; '8'; uBytes
0x180006a36  xor     ecx, ecx; uFlags
0x180006a38  mov     rbx, rax
0x180006a3b  call    cs:__imp_LocalAlloc
0x180006a41  mov     rdi, rax
0x180006a44  test    rax, rax
0x180006a47  jz      loc_180006E92
0x180006a4d  test    rbx, rbx
0x180006a50  jz      short loc_180006A6B
0x180006a52  mov     ecx, r12d
0x180006a55  lea     rdx, [rbp+57h+var_D0]
0x180006a59  call    SecpGetBinding
0x180006a5e  test    eax, eax
0x180006a60  jns     short loc_180006AA0
0x180006a62  mov     rcx, rbx; hMem
0x180006a65  call    cs:__imp_LocalFree
0x180006a6b  mov     rcx, rdi; hMem
0x180006a6e  call    cs:__imp_LocalFree
0x180006a74  inc     r12d
0x180006a77  cmp     r12d, cs:SecLsaPackageCount
0x180006a7e  jb      short loc_180006A21
0x180006a80  mov     cs:?SecPackageLsaLoaded@@3HA, 1; int SecPackageLsaLoaded
0x180006a8a  xor     eax, eax
0x180006a8c  add     rsp, 0E8h
0x180006a93  pop     r15
0x180006a95  pop     r14
0x180006a97  pop     r13
0x180006a99  pop     r12
0x180006a9b  pop     rdi
0x180006a9c  pop     rsi
0x180006a9d  pop     rbx
0x180006a9e  pop     rbp
0x180006a9f  retn
0x180006aa0  mov     rcx, cs:WPP_GLOBAL_Control
0x180006aa7  lea     rax, WPP_GLOBAL_Control
0x180006aae  mov     r14, [rbp+57h+Buffer]
0x180006ab2  cmp     rcx, rax
0x180006ab5  jnz     loc_180006E21
0x180006abb  mov     eax, [rbp+57h+var_CE]
0x180006abe  lea     r15, [rbx+60h]
0x180006ac2  movzx   esi, [rbp+57h+var_D0]
0x180006ac6  xor     ecx, ecx; uFlags
0x180006ac8  mov     dword ptr [rsp+120h+var_F0.MaximumLength], eax
0x180006acc  movzx   eax, [rbp+57h+var_CA]
0x180006ad0  mov     [rsp+120h+var_F0.Length], si
0x180006ad5  lea     rdx, [rsi+2]; uBytes
0x180006ad9  mov     word ptr [rsp+120h+var_F0+6], ax
0x180006ade  mov     [rsp+120h+var_F0.Buffer], r14
0x180006ae3  call    cs:__imp_LocalAlloc
0x180006ae9  mov     [r15+8], rax
0x180006aed  test    rax, rax
0x180006af0  jz      short loc_180006AFF
0x180006af2  lea     ecx, [rsi+2]
0x180006af5  mov     [r15+2], cx
0x180006afa  cmp     cx, si
0x180006afd  jnb     short loc_180006B16
0x180006aff  xor     edx, edx
0x180006b01  mov     rcx, rbx
0x180006b04  call    SecpFreePackage
0x180006b09  mov     rcx, r14; Buffer
0x180006b0c  call    LsaFreeReturnBuffer
0x180006b11  jmp     loc_180006A6B
0x180006b16  mov     r8, rsi; Size
0x180006b19  mov     [r15], si
0x180006b1d  mov     rdx, r14; Src
0x180006b20  mov     rcx, rax; void *
0x180006b23  call    memcpy_0
0x180006b28  movzx   r8d, word ptr [r15]
0x180006b2c  xor     eax, eax
0x180006b2e  mov     rcx, [r15+8]
0x180006b32  mov     rdx, r15; SourceString
0x180006b35  shr     r8, 1
0x180006b38  mov     [rcx+r8*2], ax
0x180006b3d  mov     r8b, 1; AllocateDestinationString
0x180006b40  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x180006b45  call    cs:__imp_RtlUnicodeStringToAnsiString
0x180006b4b  test    eax, eax
0x180006b4d  js      short loc_180006AFF
0x180006b4f  mov     rax, [rsp+120h+DestinationString.Buffer]
0x180006b54  lea     r15, [rbx+70h]
0x180006b58  movzx   esi, [rbp+57h+var_C0]
0x180006b5c  xor     ecx, ecx; uFlags
0x180006b5e  mov     r13, [rbp+57h+Src]
0x180006b62  mov     [rbx+80h], rax
0x180006b69  movzx   eax, [rsp+120h+DestinationString.Length]
0x180006b6e  inc     eax
0x180006b70  mov     [rsp+120h+var_F0.Length], si
0x180006b75  mov     [rbx+88h], eax
0x180006b7b  lea     rdx, [rsi+2]; uBytes
0x180006b7f  mov     eax, [rbp+57h+var_BE]
0x180006b82  mov     dword ptr [rsp+120h+var_F0.MaximumLength], eax
0x180006b86  movzx   eax, [rbp+57h+var_BA]
0x180006b8a  mov     word ptr [rsp+120h+var_F0+6], ax
0x180006b8f  mov     [rsp+120h+var_F0.Buffer], r13
0x180006b94  call    cs:__imp_LocalAlloc
0x180006b9a  mov     [r15+8], rax
0x180006b9e  test    rax, rax
0x180006ba1  jz      loc_180006AFF
0x180006ba7  lea     ecx, [rsi+2]
0x180006baa  mov     [r15+2], cx
0x180006baf  cmp     cx, si
0x180006bb2  jb      loc_180006AFF
0x180006bb8  mov     r8d, esi; Size
0x180006bbb  mov     [r15], si
0x180006bbf  mov     rdx, r13; Src
0x180006bc2  mov     rcx, rax; void *
0x180006bc5  call    memcpy_0
0x180006bca  movzx   r8d, word ptr [r15]
0x180006bce  xor     eax, eax
0x180006bd0  mov     rcx, [r15+8]
0x180006bd4  mov     rdx, r15; SourceString
0x180006bd7  shr     r8, 1
0x180006bda  mov     [rcx+r8*2], ax
0x180006bdf  mov     r8b, 1; AllocateDestinationString
0x180006be2  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x180006be7  call    cs:__imp_RtlUnicodeStringToAnsiString
0x180006bed  test    eax, eax
0x180006bef  js      loc_180006AFF
0x180006bf5  mov     rax, [rsp+120h+DestinationString.Buffer]
0x180006bfa  lea     rsi, [rbx+0D8h]
0x180006c01  mov     [rbx+90h], rax
0x180006c08  movzx   eax, [rsp+120h+DestinationString.Length]
0x180006c0d  or      dword ptr [rbx+24h], 4
0x180006c11  inc     eax
0x180006c13  mov     [rbx+98h], eax
0x180006c19  mov     eax, [rbp+57h+var_A0]
0x180006c1c  mov     [rbx+20h], eax
0x180006c1f  mov     eax, [rbp+57h+var_9C]
0x180006c22  mov     [rbx+50h], eax
0x180006c25  movzx   eax, [rbp+57h+var_90]
0x180006c29  mov     [rbx+54h], ax
0x180006c2d  movzx   eax, [rbp+57h+var_94]
0x180006c31  mov     [rbx+56h], ax
0x180006c35  mov     eax, [rbp+57h+var_8C]
0x180006c38  mov     [rbx+5Ch], eax
0x180006c3b  lea     rax, [rsi+10h]
0x180006c3f  mov     dword ptr [rbx+10h], 32h ; '2'
0x180006c46  mov     [rbx+0D0h], rsi
0x180006c4d  mov     [rsi+18h], rax
0x180006c51  mov     [rax], rax
0x180006c54  mov     eax, [rbp+57h+var_88]
0x180006c57  test    eax, eax
0x180006c59  jnz     loc_180006E41
0x180006c5f  mov     r15d, [rbp+57h+var_98]
0x180006c63  and     r15d, 1
0x180006c67  jnz     short loc_180006CE2
0x180006c69  mov     r13, [rbp+57h+String1]
0x180006c6d  cmp     [rbx+20h], r15d
0x180006c71  jnz     loc_180006D4F
0x180006c77  xorps   xmm0, xmm0
0x180006c7a  xor     eax, eax
0x180006c7c  movups  xmmword ptr [rdi], xmm0
0x180006c7f  movups  xmmword ptr [rdi+10h], xmm0
0x180006c83  movups  xmmword ptr [rdi+20h], xmm0
0x180006c87  mov     [rdi+30h], rax
0x180006c8b  inc     dword ptr [rdi+20h]
0x180006c8e  lea     rcx, [rdi+10h]; struct _UNICODE_STRING *
0x180006c92  cmp     qword ptr [rcx+8], 0
0x180006c97  jz      short loc_180006CFA
0x180006c99  or      dword ptr [rbx+24h], 11h
0x180006c9d  mov     rcx, rbx; struct _DLL_SECURITY_PACKAGE *
0x180006ca0  mov     eax, r12d
0x180006ca3  mov     [rbx+18h], rax
0x180006ca7  mov     [rbx+28h], rax
0x180006cab  mov     [rbx+30h], rax
0x180006caf  mov     [rbx+38h], rdi
0x180006cb3  call    ?SecpAddDllPackage@@YAXPEAU_DLL_SECURITY_PACKAGE@@@Z; SecpAddDllPackage(_DLL_SECURITY_PACKAGE *)
0x180006cb8  mov     rcx, r14; Buffer
0x180006cbb  call    LsaFreeReturnBuffer
0x180006cc0  mov     rcx, rdi; hMem
0x180006cc3  call    ?SecpDerefDll@@YAXPEAU_SECP_DLL_BINDING@@@Z; SecpDerefDll(_SECP_DLL_BINDING *)
0x180006cc8  test    r15d, r15d
0x180006ccb  jz      loc_180006A74
0x180006cd1  mov     rcx, rbx; struct _DLL_SECURITY_PACKAGE *
0x180006cd4  call    ?SecpSnapNewDll@@YAJPEAU_DLL_SECURITY_PACKAGE@@@Z; SecpSnapNewDll(_DLL_SECURITY_PACKAGE *)
0x180006cd9  and     dword ptr [rbx+24h], 0FFFFFFFBh
0x180006cdd  jmp     loc_180006A74
0x180006ce2  mov     rcx, rdi; hMem
0x180006ce5  call    cs:__imp_LocalFree
0x180006ceb  inc     cs:dword_18003FE90
0x180006cf1  lea     rdi, ?SecpBuiltinBinding@@3U_SECP_DLL_BINDING@@A; _SECP_DLL_BINDING SecpBuiltinBinding
0x180006cf8  jmp     short loc_180006C99
0x180006cfa  movzx   eax, [rbp+57h+var_B0]
0x180006cfe  lea     rdx, [rsp+120h+var_F0]; struct _UNICODE_STRING *
0x180006d03  mov     [rsp+120h+var_F0.Length], ax
0x180006d08  mov     eax, [rbp+57h+var_AE]
0x180006d0b  mov     dword ptr [rsp+120h+var_F0.MaximumLength], eax
0x180006d0f  movzx   eax, [rbp+57h+var_AA]
0x180006d13  mov     word ptr [rsp+120h+var_F0+6], ax
0x180006d18  mov     dword ptr [rdi], 1
0x180006d1e  mov     [rsp+120h+var_F0.Buffer], r13
0x180006d23  call    ?SecpDuplicateString@@YAHPEAU_UNICODE_STRING@@0@Z; SecpDuplicateString(_UNICODE_STRING *,_UNICODE_STRING *)
0x180006d28  test    eax, eax
0x180006d2a  jnz     loc_180006E7D
0x180006d30  xor     edx, edx
0x180006d32  mov     rcx, rbx
0x180006d35  call    SecpFreePackage
0x180006d3a  mov     rcx, r14; Buffer
0x180006d3d  call    LsaFreeReturnBuffer
0x180006d42  mov     rcx, rdi; hMem
0x180006d45  call    ?SecpDerefDll@@YAXPEAU_SECP_DLL_BINDING@@@Z; SecpDerefDll(_SECP_DLL_BINDING *)
0x180006d4a  jmp     loc_180006A74
0x180006d4f  movzx   eax, [rbp+57h+var_B0]
0x180006d53  mov     [rsp+120h+var_F0.Length], ax
0x180006d58  mov     eax, [rbp+57h+var_AE]
0x180006d5b  mov     dword ptr [rsp+120h+var_F0.MaximumLength], eax
0x180006d5f  movzx   eax, [rbp+57h+var_AA]
0x180006d63  mov     word ptr [rsp+120h+var_F0+6], ax
0x180006d68  mov     rax, gs:30h
0x180006d71  mov     ecx, cs:SecPackageListLockCount
0x180006d77  dec     ecx
0x180006d79  mov     [rsp+120h+var_F0.Buffer], r13
0x180006d7e  movzx   edx, byte ptr [rax+1747h]
0x180006d85  and     rdx, rcx
0x180006d88  lea     rcx, SecPackageListLock
0x180006d8f  lea     rax, [rdx+rdx*2]
0x180006d93  mov     dl, 1; Wait
0x180006d95  shl     rax, 5
0x180006d99  add     rax, rcx
0x180006d9c  mov     rcx, rax; Resource
0x180006d9f  mov     [rbp+57h+Resource], rax
0x180006da3  call    cs:__imp_RtlAcquireResourceShared
0x180006da9  mov     r8d, cs:?SecPackageDllCount@@3KA; ulong SecPackageDllCount
0x180006db0  xor     esi, esi
0x180006db2  test    r8d, r8d
0x180006db5  jz      short loc_180006E1D
0x180006db7  mov     rax, cs:?SecPackageDllList@@3PEAPEAU_SECP_DLL_BINDING@@EA; _SECP_DLL_BINDING * * SecPackageDllList
0x180006dbe  mov     rdx, [rax+rsi*8]
0x180006dc2  test    rdx, rdx
0x180006dc5  jz      short loc_180006DDF
0x180006dc7  mov     rdx, [rdx+18h]; String2
0x180006dcb  mov     rcx, r13; String1
0x180006dce  call    cs:__imp__wcsicmp
0x180006dd4  mov     r8d, cs:?SecPackageDllCount@@3KA; ulong SecPackageDllCount
0x180006ddb  test    eax, eax
0x180006ddd  jz      short loc_180006DE6
0x180006ddf  inc     esi
0x180006de1  cmp     esi, r8d
0x180006de4  jb      short loc_180006DB7
0x180006de6  cmp     esi, r8d
0x180006de9  jnb     short loc_180006E1D
0x180006deb  lfence
0x180006dee  mov     rax, cs:?SecPackageDllList@@3PEAPEAU_SECP_DLL_BINDING@@EA; _SECP_DLL_BINDING * * SecPackageDllList
0x180006df5  mov     rsi, [rax+rsi*8]
0x180006df9  mov     rcx, [rbp+57h+Resource]; Resource
0x180006dfd  call    cs:__imp_RtlReleaseResource
0x180006e03  test    rsi, rsi
0x180006e06  jz      loc_180006C77
0x180006e0c  mov     rcx, rdi; hMem
0x180006e0f  call    cs:__imp_LocalFree
0x180006e15  mov     rdi, rsi
0x180006e18  jmp     loc_180006C8B
0x180006e1d  xor     esi, esi
0x180006e1f  jmp     short loc_180006DF9
0x180006e21  test    byte ptr [rcx+1Ch], 4
0x180006e25  jz      loc_180006ABB
0x180006e2b  mov     rcx, [rcx+10h]
0x180006e2f  mov     r9d, r12d
0x180006e32  mov     [rsp+120h+var_100], r14
0x180006e37  call    WPP_SF_dS
0x180006e3c  jmp     loc_180006ABB
0x180006e41  mov     r15, rax
0x180006e44  mov     [rsi], eax
0x180006e46  shl     r15, 2
0x180006e4a  xor     ecx, ecx; uFlags
0x180006e4c  mov     rdx, r15; uBytes
0x180006e4f  call    cs:__imp_LocalAlloc
0x180006e55  mov     [rsi+8], rax
0x180006e59  test    rax, rax
0x180006e5c  jz      short loc_180006E72
0x180006e5e  mov     r8, r15; Size
0x180006e61  lea     rdx, [rbp+57h+var_84]; Src
0x180006e65  mov     rcx, rax; void *
0x180006e68  call    memcpy_0
  ... truncated ...
```
