# SampRegistryDelnode(ushort const *)

- ea: `0x18006fdbc`
- end: `0x1800702b4`
- name: `?SampRegistryDelnode@@YAJPEBG@Z`
- size: `1272`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006fdbc`
- `0x180071870`
- `0x180071af0`
- `0x1800722d0`
- `0x1800799a8`

## callees

- `0x180027e24`
- `0x18002cd80`
- `0x18005308c`
- `0x18006af10`
- `0x18006fdbc`
- `0x1800aa040`

## import_xrefs

- `ntdll!NtDeleteKey` at `0x180070251`
- `ntdll!NtDeleteKey` at `0x180070251`
- `ntdll!NtEnumerateKey` at `0x18007000a`
- `ntdll!NtEnumerateKey` at `0x180070066`
- `ntdll!NtEnumerateKey` at `0x18007000a`
- `ntdll!NtEnumerateKey` at `0x180070066`
- `ntdll!NtQueryKey` at `0x18006fee8`
- `ntdll!NtQueryKey` at `0x18006ff47`
- `ntdll!NtQueryKey` at `0x18006fee8`
- `ntdll!NtQueryKey` at `0x18006ff47`
- `ntdll!NtOpenKey` at `0x18006fe8c`
- `ntdll!NtOpenKey` at `0x18006fe8c`
- `ntdll!NtClose` at `0x1800701da`
- `ntdll!NtClose` at `0x1800701da`
- `ntdll!RtlInitUnicodeString` at `0x18006fe52`
- `ntdll!RtlInitUnicodeString` at `0x18006fe52`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006ff0e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006ff68`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007002f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006ff0e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006ff68`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007002f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070161`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070177`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070195`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800701a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800701ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800701cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070161`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070177`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070195`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800701a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800701ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800701cf`

## pseudocode

```c
__int64 __fastcall SampRegistryDelnode(const unsigned __int16 *a1)
{
  ULONG v1; // r14d
  __int64 v3; // rcx
  unsigned __int64 v4; // rdi
  _BYTE *v5; // rax
  NTSTATUS v6; // ebx
  PUNICODE_STRING v7; // rcx
  __int64 v8; // rdx
  NTSTATUS v10; // eax
  _DWORD *v11; // r15
  ULONG v12; // r13d
  SIZE_T v13; // rsi
  _BYTE *v14; // rax
  _BYTE *v15; // rax
  __int64 v16; // rcx
  NTSTATUS v17; // eax
  unsigned int *v18; // rdi
  unsigned __int64 v19; // r14
  _WORD *v20; // r12
  unsigned __int64 v21; // r14
  unsigned __int64 v22; // rcx
  _WORD *v23; // rax
  int v24; // edx
  const unsigned __int16 **v25; // r12
  ULONG k; // esi
  unsigned __int16 *v27; // rcx
  ULONG j; // edi
  PULONG ResultLength; // [rsp+20h] [rbp-E0h]
  char v30; // [rsp+30h] [rbp-D0h]
  char v31; // [rsp+31h] [rbp-CFh]
  ULONG Length; // [rsp+34h] [rbp-CCh] BYREF
  ULONG v33; // [rsp+38h] [rbp-C8h] BYREF
  HLOCAL v34; // [rsp+40h] [rbp-C0h]
  void *KeyHandle; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v36[2]; // [rsp+50h] [rbp-B0h] BYREF
  int i; // [rsp+58h] [rbp-A8h]
  HLOCAL v38; // [rsp+60h] [rbp-A0h] BYREF
  const unsigned __int16 *v39; // [rsp+68h] [rbp-98h]
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-80h] BYREF
  _BYTE hMem[64]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE KeyInformation[80]; // [rsp+F0h] [rbp-10h] BYREF

  v1 = 0;
  v39 = a1;
  KeyHandle = 0;
  v38 = 0;
  v36[0] = 0;
  v3 = 80;
  Length = 80;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  if ( a1 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a1[v4] );
    if ( v4 <= 0x104 )
    {
      v5 = KeyInformation;
      do
      {
        *v5++ = 0;
        --v3;
      }
      while ( v3 );
      RtlInitUnicodeString(&DestinationString, a1);
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v6 = NtOpenKey(&KeyHandle, 0xF003Fu, &ObjectAttributes);
      if ( v6 < 0 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
          return (unsigned int)v6;
        v8 = 121;
LABEL_10:
        WPP_SF_Dd(v7[3].Buffer, v8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, (unsigned int)v6, v6);
        return (unsigned int)v6;
      }
      v10 = NtQueryKey(KeyHandle, KeyFullInformation, KeyInformation, Length, &Length);
      v6 = v10;
      if ( v10 == -2147483643 || (v31 = 0, v11 = KeyInformation, v10 == -1073741789) )
      {
        v11 = LocalAlloc(0x40u, Length);
        if ( !v11 )
        {
          v6 = -1073741801;
LABEL_62:
          NtClose(KeyHandle);
          v7 = WPP_GLOBAL_Control;
          if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
            return (unsigned int)v6;
          v8 = 122;
          goto LABEL_10;
        }
        v31 = 1;
        v6 = NtQueryKey(KeyHandle, KeyFullInformation, v11, Length, &Length);
      }
      if ( v6 >= 0 )
      {
        v12 = v11[5];
        v13 = 8LL * v12;
        v14 = LocalAlloc(0x40u, v13);
        v34 = v14;
        if ( v14 )
        {
          v30 = 0;
          for ( i = 2 * v4 + 6; v13; --v13 )
            *v14++ = 0;
          while ( 1 )
          {
            v36[1] = v1;
            if ( v1 >= v12 )
              break;
            if ( v6 < 0 )
            {
              v25 = (const unsigned __int16 **)v34;
              goto LABEL_71;
            }
            v33 = 56;
            v15 = hMem;
            v30 = 0;
            v16 = 56;
            do
            {
              *v15++ = 0;
              --v16;
            }
            while ( v16 );
            v17 = NtEnumerateKey(KeyHandle, v1, KeyBasicInformation, hMem, 0x38u, &v33);
            v6 = v17;
            if ( v17 == -2147483643 || v17 == -1073741789 )
            {
              v18 = (unsigned int *)LocalAlloc(0x40u, v33);
              if ( !v18 )
              {
                v6 = -1073741801;
                goto LABEL_51;
              }
              v30 = 1;
              v6 = NtEnumerateKey(KeyHandle, v1, KeyBasicInformation, v18, v33, &v33);
            }
            else
            {
              v18 = (unsigned int *)hMem;
            }
            if ( v6 >= 0 )
            {
              LODWORD(ResultLength) = i;
              v6 = MIDL_user_allocate_safeadd(&v38, v36, 2u, v18[3], ResultLength);
              if ( v6 < 0 )
                goto LABEL_51;
              v19 = v36[0];
              v20 = v38;
              v6 = RtlStringCbPrintfW((unsigned __int16 *)v38, v36[0], L"%ws\\", v39);
              if ( v6 < 0 )
                goto LABEL_50;
              v21 = v19 >> 1;
              if ( !v21 )
                goto LABEL_49;
              v22 = v21;
              v23 = v20;
              do
              {
                if ( !*v23 )
                  break;
                ++v23;
                --v22;
              }
              while ( v22 );
              v6 = v22 == 0 ? 0xC000000D : 0;
              v24 = v22 ? v21 - v22 : 0;
              if ( !v22 )
                goto LABEL_50;
              if ( (unsigned __int64)v18[3] >> 1 > 0x7FFFFFFE )
              {
LABEL_49:
                v6 = -1073741811;
LABEL_50:
                LocalFree(v20);
LABEL_51:
                v25 = (const unsigned __int16 **)v34;
                goto LABEL_52;
              }
              v6 = RtlStringCopyWorkerW(
                     (int)v20 + 2 * v24,
                     (int)v21 - v24,
                     0,
                     (int)v18 + 16,
                     (unsigned __int64)v18[3] >> 1);
              if ( v6 < 0 )
                goto LABEL_50;
              v1 = v36[1];
              *((_QWORD *)v34 + v36[1]) = v20;
            }
            if ( v30 && v18 )
              LocalFree(v18);
            ++v1;
          }
          v25 = (const unsigned __int16 **)v34;
          if ( v6 >= 0 )
          {
            for ( j = 0; j < v12; ++j )
            {
              v6 = SampRegistryDelnode(v25[j]);
              if ( v6 < 0 )
                break;
            }
          }
LABEL_71:
          v18 = 0;
          if ( v6 >= 0 )
            v6 = NtDeleteKey(KeyHandle);
LABEL_52:
          for ( k = 0; k < v12; ++k )
          {
            v27 = (unsigned __int16 *)v25[k];
            if ( v27 )
              LocalFree(v27);
          }
          LocalFree(v25);
          if ( v30 && v18 )
            LocalFree(v18);
        }
        else
        {
          v6 = -1073741801;
        }
      }
      if ( v31 )
      {
        if ( v11 )
          LocalFree(v11);
      }
      goto LABEL_62;
    }
  }
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control[3].Buffer,
      120,
      WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids,
      3221225485LL,
      -1073741811);
  return 3221225485LL;
}

```

## disassembly

```asm
0x18006fdbc  push    rbp
0x18006fdbe  push    rbx
0x18006fdbf  push    rsi
0x18006fdc0  push    rdi
0x18006fdc1  push    r12
0x18006fdc3  push    r13
0x18006fdc5  push    r14
0x18006fdc7  push    r15
0x18006fdc9  lea     rbp, [rsp-58h]
0x18006fdce  sub     rsp, 158h
0x18006fdd5  mov     rax, cs:__security_cookie
0x18006fddc  xor     rax, rsp
0x18006fddf  mov     [rbp+90h+var_50], rax
0x18006fde3  xor     r14d, r14d
0x18006fde6  mov     [rsp+190h+var_128], rcx
0x18006fdeb  xorps   xmm0, xmm0
0x18006fdee  mov     [rsp+190h+KeyHandle], r14
0x18006fdf3  mov     rdx, rcx; SourceString
0x18006fdf6  mov     [rsp+190h+var_130], r14
0x18006fdfb  mov     [rsp+190h+var_140], r14d
0x18006fe00  lea     ecx, [r14+50h]
0x18006fe04  mov     [rsp+190h+Length], ecx
0x18006fe08  movups  xmmword ptr [rbp+90h+ObjectAttributes.Length], xmm0
0x18006fe0c  movups  xmmword ptr [rbp+90h+ObjectAttributes.ObjectName], xmm0
0x18006fe10  movups  xmmword ptr [rbp+90h+ObjectAttributes.SecurityDescriptor], xmm0
0x18006fe14  movups  xmmword ptr [rsp+190h+DestinationString.Length], xmm0
0x18006fe19  test    rdx, rdx
0x18006fe1c  jz      loc_18007025E
0x18006fe22  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18006fe26  inc     rdi
0x18006fe29  cmp     [rdx+rdi*2], r14w
0x18006fe2e  jnz     short loc_18006FE26
0x18006fe30  cmp     rdi, 104h
0x18006fe37  ja      loc_18007025E
0x18006fe3d  lea     rax, [rbp+90h+KeyInformation]
0x18006fe41  mov     [rax], r14b
0x18006fe44  inc     rax
0x18006fe47  sub     rcx, 1
0x18006fe4b  jnz     short loc_18006FE41
0x18006fe4d  lea     rcx, [rsp+190h+DestinationString]; DestinationString
0x18006fe52  call    cs:__imp_RtlInitUnicodeString
0x18006fe58  lea     rax, [rsp+190h+DestinationString]
0x18006fe5d  mov     [rbp+90h+ObjectAttributes.Length], 30h ; '0'
0x18006fe64  xorps   xmm0, xmm0
0x18006fe67  mov     [rbp+90h+ObjectAttributes.ObjectName], rax
0x18006fe6b  mov     r12d, 40h ; '@'
0x18006fe71  mov     [rbp+90h+ObjectAttributes.RootDirectory], r14
0x18006fe75  lea     r8, [rbp+90h+ObjectAttributes]; ObjectAttributes
0x18006fe79  mov     [rbp+90h+ObjectAttributes.Attributes], r12d
0x18006fe7d  mov     edx, 0F003Fh; DesiredAccess
0x18006fe82  lea     rcx, [rsp+190h+KeyHandle]; KeyHandle
0x18006fe87  movdqu  xmmword ptr [rbp+90h+ObjectAttributes.SecurityDescriptor], xmm0
0x18006fe8c  call    cs:__imp_NtOpenKey
0x18006fe92  mov     ebx, eax
0x18006fe94  test    eax, eax
0x18006fe96  jns     short loc_18006FECB
0x18006fe98  mov     rcx, cs:WPP_GLOBAL_Control
0x18006fe9f  test    dword ptr [rcx+44h], 20000h
0x18006fea6  jz      short loc_18006FEC4
0x18006fea8  lea     edx, [r12+39h]
0x18006fead  mov     rcx, [rcx+38h]
0x18006feb1  lea     r8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x18006feb8  mov     r9d, ebx
0x18006febb  mov     dword ptr [rsp+190h+ResultLength], ebx
0x18006febf  call    WPP_SF_Dd
0x18006fec4  mov     eax, ebx
0x18006fec6  jmp     loc_180070294
0x18006fecb  mov     r9d, [rsp+190h+Length]; Length
0x18006fed0  lea     rax, [rsp+190h+Length]
0x18006fed5  mov     rcx, [rsp+190h+KeyHandle]; KeyHandle
0x18006feda  lea     r8, [rbp+90h+KeyInformation]; KeyInformation
0x18006fede  mov     edx, 2; KeyInformationClass
0x18006fee3  mov     [rsp+190h+ResultLength], rax; ResultLength
0x18006fee8  call    cs:__imp_NtQueryKey
0x18006feee  mov     ebx, eax
0x18006fef0  cmp     eax, 80000005h
0x18006fef5  jz      short loc_18006FF07
0x18006fef7  mov     [rsp+190h+var_15F], r14b
0x18006fefc  lea     r15, [rbp+90h+KeyInformation]
0x18006ff00  cmp     eax, 0C0000023h
0x18006ff05  jnz     short loc_18006FF4F
0x18006ff07  mov     edx, [rsp+190h+Length]; uBytes
0x18006ff0b  mov     ecx, r12d; uFlags
0x18006ff0e  call    cs:__imp_LocalAlloc
0x18006ff14  mov     r15, rax
0x18006ff17  test    rax, rax
0x18006ff1a  jnz     short loc_18006FF26
0x18006ff1c  mov     ebx, 0C0000017h
0x18006ff21  jmp     loc_1800701D5
0x18006ff26  mov     r9d, [rsp+190h+Length]; Length
0x18006ff2b  lea     rax, [rsp+190h+Length]
0x18006ff30  mov     rcx, [rsp+190h+KeyHandle]; KeyHandle
0x18006ff35  mov     r8, r15; KeyInformation
0x18006ff38  mov     edx, 2; KeyInformationClass
0x18006ff3d  mov     [rsp+190h+ResultLength], rax; ResultLength
0x18006ff42  mov     [rsp+190h+var_15F], 1
0x18006ff47  call    cs:__imp_NtQueryKey
0x18006ff4d  mov     ebx, eax
0x18006ff4f  test    ebx, ebx
0x18006ff51  js      loc_1800701C0
0x18006ff57  mov     r13d, [r15+14h]
0x18006ff5b  mov     ecx, r12d; uFlags
0x18006ff5e  mov     esi, r13d
0x18006ff61  shl     rsi, 3
0x18006ff65  mov     rdx, rsi; uBytes
0x18006ff68  call    cs:__imp_LocalAlloc
0x18006ff6e  mov     [rsp+190h+var_150], rax
0x18006ff73  mov     r12, rax
0x18006ff76  test    rax, rax
0x18006ff79  jnz     short loc_18006FF85
0x18006ff7b  mov     ebx, 0C0000017h
0x18006ff80  jmp     loc_1800701C0
0x18006ff85  mov     [rsp+190h+var_160], r14b
0x18006ff8a  lea     eax, ds:6[rdi*2]
0x18006ff91  mov     [rsp+190h+var_138], eax
0x18006ff95  mov     rax, r12
0x18006ff98  test    rsi, rsi
0x18006ff9b  jz      short loc_18006FFA9
0x18006ff9d  mov     [rax], r14b
0x18006ffa0  inc     rax
0x18006ffa3  sub     rsi, 1
0x18006ffa7  jnz     short loc_18006FF9D
0x18006ffa9  mov     esi, 0C000000Dh
0x18006ffae  xor     r12d, r12d
0x18006ffb1  mov     [rsp+190h+var_140+4], r14d
0x18006ffb6  cmp     r14d, r13d
0x18006ffb9  jnb     loc_18007020B
0x18006ffbf  test    ebx, ebx
0x18006ffc1  js      loc_180070239
0x18006ffc7  mov     [rsp+190h+var_158], 38h ; '8'
0x18006ffcf  lea     rax, [rbp+90h+hMem]
0x18006ffd3  mov     [rsp+190h+var_160], r12b
0x18006ffd8  mov     ecx, 38h ; '8'
0x18006ffdd  mov     [rax], r12b
0x18006ffe0  inc     rax
0x18006ffe3  sub     rcx, 1
0x18006ffe7  jnz     short loc_18006FFDD
0x18006ffe9  mov     rcx, [rsp+190h+KeyHandle]; KeyHandle
0x18006ffee  lea     rax, [rsp+190h+var_158]
0x18006fff3  mov     [rsp+190h+var_168], rax; ResultLength
0x18006fff8  lea     r9, [rbp+90h+hMem]; KeyInformation
0x18006fffc  xor     r8d, r8d; KeyInformationClass
0x18006ffff  mov     dword ptr [rsp+190h+ResultLength], 38h ; '8'; Length
0x180070007  mov     edx, r14d; Index
0x18007000a  call    cs:__imp_NtEnumerateKey
0x180070010  mov     ebx, eax
0x180070012  cmp     eax, 80000005h
0x180070017  jz      short loc_180070026
0x180070019  cmp     eax, 0C0000023h
0x18007001e  jz      short loc_180070026
0x180070020  lea     rdi, [rbp+90h+hMem]
0x180070024  jmp     short loc_18007006E
0x180070026  mov     edx, [rsp+190h+var_158]; uBytes
0x18007002a  mov     ecx, 40h ; '@'; uFlags
0x18007002f  call    cs:__imp_LocalAlloc
0x180070035  mov     rdi, rax
0x180070038  test    rax, rax
0x18007003b  jz      loc_1800701FE
0x180070041  mov     ecx, [rsp+190h+var_158]
0x180070045  lea     rax, [rsp+190h+var_158]
0x18007004a  mov     [rsp+190h+var_168], rax; ResultLength
0x18007004f  mov     r9, rdi; KeyInformation
0x180070052  mov     dword ptr [rsp+190h+ResultLength], ecx; Length
0x180070056  xor     r8d, r8d; KeyInformationClass
0x180070059  mov     rcx, [rsp+190h+KeyHandle]; KeyHandle
0x18007005e  mov     edx, r14d; Index
0x180070061  mov     [rsp+190h+var_160], 1
0x180070066  call    cs:__imp_NtEnumerateKey
0x18007006c  mov     ebx, eax
0x18007006e  test    ebx, ebx
0x180070070  js      loc_180070152
0x180070076  mov     eax, [rsp+190h+var_138]
0x18007007a  lea     rdx, [rsp+190h+var_140]; unsigned int *
0x18007007f  mov     r9d, [rdi+0Ch]
0x180070083  lea     rcx, [rsp+190h+var_130]; void **
0x180070088  mov     r8d, 2; unsigned int
0x18007008e  mov     dword ptr [rsp+190h+ResultLength], eax
0x180070092  call    ?MIDL_user_allocate_safeadd@@YAJPEAPEAXPEAKKZZ; MIDL_user_allocate_safeadd(void * *,ulong *,ulong,...)
0x180070097  xor     r14d, r14d
0x18007009a  mov     ebx, eax
0x18007009c  test    eax, eax
0x18007009e  js      loc_18007017D
0x1800700a4  mov     r14d, [rsp+190h+var_140]
0x1800700a9  lea     r8, aWs; "%ws\\"
0x1800700b0  mov     r12, [rsp+190h+var_130]
0x1800700b5  mov     edx, r14d; unsigned __int64
0x1800700b8  mov     r9, [rsp+190h+var_128]
0x1800700bd  mov     rcx, r12; unsigned __int16 *
0x1800700c0  call    ?RtlStringCbPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800700c5  xor     r8d, r8d
0x1800700c8  mov     ebx, eax
0x1800700ca  test    eax, eax
0x1800700cc  js      loc_180070171
0x1800700d2  shr     r14, 1
0x1800700d5  jz      loc_18007016F
0x1800700db  mov     rcx, r14
0x1800700de  mov     rax, r12
0x1800700e1  cmp     [rax], r8w
0x1800700e5  jz      short loc_1800700F1
0x1800700e7  add     rax, 2
0x1800700eb  sub     rcx, 1
0x1800700ef  jnz     short loc_1800700E1
0x1800700f1  mov     rax, rcx
0x1800700f4  neg     rax
0x1800700f7  sbb     ebx, ebx
0x1800700f9  not     ebx
0x1800700fb  and     ebx, esi
0x1800700fd  test    rcx, rcx
0x180070100  jz      short loc_18007010A
0x180070102  mov     rdx, r14
0x180070105  sub     rdx, rcx
0x180070108  jmp     short loc_18007010D
0x18007010a  mov     rdx, r8
0x18007010d  test    rcx, rcx
0x180070110  jz      short loc_180070171
0x180070112  mov     eax, [rdi+0Ch]
0x180070115  shr     rax, 1
0x180070118  cmp     rax, 7FFFFFFEh
0x18007011e  ja      short loc_18007016F
0x180070120  sub     r14, rdx
0x180070123  mov     [rsp+190h+ResultLength], rax
0x180070128  lea     rcx, [r12+rdx*2]
0x18007012c  mov     rdx, r14
0x18007012f  lea     r9, [rdi+10h]
0x180070133  call    RtlStringCopyWorkerW
0x180070138  xor     r14d, r14d
0x18007013b  mov     ebx, eax
0x18007013d  test    eax, eax
0x18007013f  js      short loc_180070174
0x180070141  mov     r14d, [rsp+190h+var_140+4]
0x180070146  mov     rcx, [rsp+190h+var_150]
0x18007014b  mov     [rcx+r14*8], r12
0x18007014f  xor     r12d, r12d
0x180070152  cmp     [rsp+190h+var_160], r12b
0x180070157  jz      short loc_180070167
0x180070159  test    rdi, rdi
0x18007015c  jz      short loc_180070167
0x18007015e  mov     rcx, rdi; hMem
0x180070161  call    cs:__imp_LocalFree
0x180070167  inc     r14d
0x18007016a  jmp     loc_18006FFB1
0x18007016f  mov     ebx, esi
0x180070171  xor     r14d, r14d
0x180070174  mov     rcx, r12; hMem
0x180070177  call    cs:__imp_LocalFree
0x18007017d  mov     r12, [rsp+190h+var_150]
0x180070182  mov     esi, r14d
0x180070185  test    r13d, r13d
0x180070188  jz      short loc_1800701A2
0x18007018a  mov     eax, esi
0x18007018c  mov     rcx, [r12+rax*8]; hMem
0x180070190  test    rcx, rcx
0x180070193  jz      short loc_18007019B
0x180070195  call    cs:__imp_LocalFree
0x18007019b  inc     esi
0x18007019d  cmp     esi, r13d
0x1800701a0  jb      short loc_18007018A
0x1800701a2  mov     rcx, r12; hMem
0x1800701a5  call    cs:__imp_LocalFree
0x1800701ab  cmp     [rsp+190h+var_160], r14b
0x1800701b0  jz      short loc_1800701C0
0x1800701b2  test    rdi, rdi
0x1800701b5  jz      short loc_1800701C0
0x1800701b7  mov     rcx, rdi; hMem
0x1800701ba  call    cs:__imp_LocalFree
0x1800701c0  cmp     [rsp+190h+var_15F], r14b
0x1800701c5  jz      short loc_1800701D5
0x1800701c7  test    r15, r15
0x1800701ca  jz      short loc_1800701D5
0x1800701cc  mov     rcx, r15; hMem
0x1800701cf  call    cs:__imp_LocalFree
0x1800701d5  mov     rcx, [rsp+190h+KeyHandle]; Handle
0x1800701da  call    cs:__imp_NtClose
0x1800701e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800701e7  test    dword ptr [rcx+44h], 20000h
0x1800701ee  jz      loc_18006FEC4
0x1800701f4  mov     edx, 7Ah ; 'z'
0x1800701f9  jmp     loc_18006FEAD
0x1800701fe  mov     ebx, 0C0000017h
0x180070203  xor     r14d, r14d
0x180070206  jmp     loc_18007017D
0x18007020b  mov     r12, [rsp+190h+var_150]
0x180070210  xor     r14d, r14d
0x180070213  test    ebx, ebx
0x180070215  js      short loc_180070241
0x180070217  mov     edi, r14d
0x18007021a  test    r13d, r13d
0x18007021d  jz      short loc_180070241
0x18007021f  mov     ecx, edi
0x180070221  mov     rcx, [r12+rcx*8]; unsigned __int16 *
0x180070225  call    ?SampRegistryDelnode@@YAJPEBG@Z; SampRegistryDelnode(ushort const *)
0x18007022a  mov     ebx, eax
0x18007022c  test    eax, eax
0x18007022e  js      short loc_180070241
0x180070230  inc     edi
0x180070232  cmp     edi, r13d
0x180070235  jb      short loc_18007021F
0x180070237  jmp     short loc_180070241
0x180070239  mov     r12, [rsp+190h+var_150]
0x18007023e  xor     r14d, r14d
  ... truncated ...
```
