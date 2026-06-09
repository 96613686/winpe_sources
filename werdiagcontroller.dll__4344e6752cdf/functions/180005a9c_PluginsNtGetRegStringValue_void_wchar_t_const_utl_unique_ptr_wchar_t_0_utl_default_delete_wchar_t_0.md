# PluginsNtGetRegStringValue(void *,wchar_t const *,utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *)

- ea: `0x180005a9c`
- end: `0x180005d1b`
- name: `?PluginsNtGetRegStringValue@@YAJPEAXPEB_WPEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@@Z`
- size: `639`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, const WCHAR *, void **)`
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180002234`
- `0x1800028d0`
- `0x1800034cc`
- `0x180003e10`
- `0x180005158`

## callees

- `0x180001cd4`
- `0x180001ce0`
- `0x180001d10`
- `0x180003b58`
- `0x180005a9c`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180005ad9`
- `ntdll!RtlInitUnicodeString` at `0x180005ad9`
- `ntdll!DbgPrintEx` at `0x180005b3f`
- `ntdll!DbgPrintEx` at `0x180005b66`
- `ntdll!DbgPrintEx` at `0x180005c93`
- `ntdll!DbgPrintEx` at `0x180005cc4`
- `ntdll!DbgPrintEx` at `0x180005ce2`
- `ntdll!DbgPrintEx` at `0x180005cff`
- `ntdll!DbgPrintEx` at `0x180005b3f`
- `ntdll!DbgPrintEx` at `0x180005b66`
- `ntdll!DbgPrintEx` at `0x180005c93`
- `ntdll!DbgPrintEx` at `0x180005cc4`
- `ntdll!DbgPrintEx` at `0x180005ce2`
- `ntdll!DbgPrintEx` at `0x180005cff`
- `ntdll!NtQueryValueKey` at `0x180005b1e`
- `ntdll!NtQueryValueKey` at `0x180005b1e`

## string_xrefs

- `0x180005b31`: `WERDIAG: Failed extracting registry value %S. NTSTATUS: %08X\n`
- `0x180005c7c`: `WERDIAG: Failed copying string. NTSTATUS: %08X\n`
- `0x180005b53`: `WERDIAG: Registry value %S is not of type string\n`

## pseudocode

```c
__int64 __fastcall PluginsNtGetRegStringValue(HANDLE KeyHandle, const WCHAR *a2, void **a3)
{
  _DWORD *v6; // rdi
  NTSTATUS v7; // eax
  unsigned int v8; // ebx
  _WORD *v9; // r14
  __int64 v10; // rcx
  _WORD *v11; // rax
  unsigned __int64 v12; // r8
  unsigned __int64 v13; // rsi
  void **unique_for; // rax
  void *v15; // rdx
  void *v16; // rcx
  _WORD *v17; // rdx
  __int64 v18; // rax
  _WORD *v19; // rcx
  struct _UNICODE_STRING ValueName; // [rsp+30h] [rbp-38h] BYREF
  ULONG ResultLength; // [rsp+78h] [rbp+10h] BYREF
  void *v23; // [rsp+88h] [rbp+20h] BYREF

  ResultLength = 0;
  ValueName = 0;
  if ( a2 && KeyHandle )
  {
    RtlInitUnicodeString(&ValueName, a2);
    v6 = operator new(0x80Fu, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v6 )
    {
      DbgPrintEx(0x96u, 0, "WERDIAG: Out of resources allocating memory for key information structure\n");
      return (unsigned int)-1073741670;
    }
    v7 = NtQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, v6, 0x80Fu, &ResultLength);
    v8 = v7;
    if ( v7 >= 0 )
    {
      if ( v6[1] == 1 )
      {
        v9 = v6 + 3;
        if ( v6 == (_DWORD *)-12LL || (v10 = ResultLength, ResultLength > 0x7FFFFFFFuLL) )
        {
          v8 = -1073741811;
        }
        else
        {
          v11 = v6 + 3;
          if ( ResultLength )
          {
            do
            {
              if ( !*v11 )
                break;
              ++v11;
              --v10;
            }
            while ( v10 );
          }
          v8 = -1073741811;
          if ( v10 )
            v12 = ResultLength - v10;
          else
            v12 = 0;
          if ( v10 )
          {
            v13 = v12 + 1;
            if ( v12 + 1 < v12 )
            {
              v8 = -1073741675;
              DbgPrintEx(0x96u, 0, "WERDIAG: RtlSizeTAdd failed. NTSTATUS: %08X\n", 3221225621LL);
              goto LABEL_40;
            }
            unique_for = (void **)utl::make_unique_for_overwrite<wchar_t [0],0>(&v23, v12 + 1);
            v15 = *unique_for;
            *unique_for = 0;
            v16 = *a3;
            *a3 = v15;
            if ( v16 )
              operator delete[](v16);
            if ( v23 )
              operator delete[](v23);
            v17 = *a3;
            if ( !*a3 )
            {
              DbgPrintEx(0x96u, 0, "WERDIAG: Out of resources allocating memory for string buffer\n");
              v8 = -1073741670;
              goto LABEL_40;
            }
            if ( v13 )
            {
              if ( v13 > 0x7FFFFFFF )
              {
                *v17 = 0;
              }
              else
              {
                v18 = 2147483646;
                do
                {
                  if ( !v18 )
                    break;
                  if ( !*v9 )
                    break;
                  *v17++ = *v9++;
                  --v18;
                  --v13;
                }
                while ( v13 );
                v19 = v17 - 1;
                v8 = v13 == 0 ? 0x80000005 : 0;
                if ( v13 )
                  v19 = v17;
                *v19 = 0;
                if ( v13 )
                {
                  v8 = 0;
                  goto LABEL_40;
                }
              }
            }
            DbgPrintEx(0x96u, 0, "WERDIAG: Failed copying string. NTSTATUS: %08X\n", v8);
            goto LABEL_40;
          }
          v8 = -1073741811;
        }
        DbgPrintEx(0x96u, 0, "WERDIAG: Failed determining string buffer length. NTSTATUS: %08X\n", 3221225485LL);
        goto LABEL_40;
      }
      v8 = -1073741823;
      DbgPrintEx(0x96u, 0, "WERDIAG: Registry value %S is not of type string\n", a2);
    }
    else
    {
      DbgPrintEx(0x96u, 0, "WERDIAG: Failed extracting registry value %S. NTSTATUS: %08X\n", a2, v7);
    }
LABEL_40:
    operator delete(v6);
    return v8;
  }
  DbgPrintEx(0x96u, 0, "WERDIAG: Invalid parameters\n");
  return 3221225485LL;
}

```

## disassembly

```asm
0x180005a9c  mov     rax, rsp
0x180005a9f  mov     [rax+8], rbx
0x180005aa3  push    rbp
0x180005aa4  push    rsi
0x180005aa5  push    rdi
0x180005aa6  push    r14
0x180005aa8  push    r15
0x180005aaa  sub     rsp, 40h
0x180005aae  xor     ebp, ebp
0x180005ab0  xorps   xmm0, xmm0
0x180005ab3  mov     [rax+10h], ebp
0x180005ab6  mov     r15, r8
0x180005ab9  mov     rsi, rdx
0x180005abc  mov     rbx, rcx
0x180005abf  movups  xmmword ptr [rax-38h], xmm0
0x180005ac3  test    rdx, rdx
0x180005ac6  jz      loc_180005CF1
0x180005acc  test    rcx, rcx
0x180005acf  jz      loc_180005CF1
0x180005ad5  lea     rcx, [rax-38h]; DestinationString
0x180005ad9  call    cs:__imp_RtlInitUnicodeString
0x180005adf  mov     r14d, 80Fh
0x180005ae5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005aec  mov     ecx, r14d; unsigned __int64
0x180005aef  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180005af4  mov     rdi, rax
0x180005af7  test    rax, rax
0x180005afa  jz      loc_180005CD4
0x180005b00  lea     rax, [rsp+68h+arg_8]
0x180005b05  mov     r9, rdi; KeyValueInformation
0x180005b08  mov     [rsp+68h+ResultLength], rax; ResultLength
0x180005b0d  lea     r8d, [rbp+2]; KeyValueInformationClass
0x180005b11  lea     rdx, [rsp+68h+ValueName]; ValueName
0x180005b16  mov     [rsp+68h+Length], r14d; Length
0x180005b1b  mov     rcx, rbx; KeyHandle
0x180005b1e  call    cs:__imp_NtQueryValueKey
0x180005b24  mov     ebx, eax
0x180005b26  test    eax, eax
0x180005b28  jns     short loc_180005B4A
0x180005b2a  mov     r9, rsi
0x180005b2d  mov     [rsp+68h+Length], eax
0x180005b31  lea     r8, aWerdiagFailedE_2; "WERDIAG: Failed extracting registry val"...
0x180005b38  xor     edx, edx; Level
0x180005b3a  mov     ecx, 96h; ComponentId
0x180005b3f  call    cs:__imp_DbgPrintEx
0x180005b45  jmp     loc_180005CCA
0x180005b4a  cmp     dword ptr [rdi+4], 1
0x180005b4e  jz      short loc_180005B71
0x180005b50  mov     r9, rsi
0x180005b53  lea     r8, aWerdiagRegistr; "WERDIAG: Registry value %S is not of ty"...
0x180005b5a  xor     edx, edx; Level
0x180005b5c  mov     ecx, 96h; ComponentId
0x180005b61  mov     ebx, 0C0000001h
0x180005b66  call    cs:__imp_DbgPrintEx
0x180005b6c  jmp     loc_180005CCA
0x180005b71  lea     r14, [rdi+0Ch]
0x180005b75  test    r14, r14
0x180005b78  jz      loc_180005CAE
0x180005b7e  mov     ecx, [rsp+68h+arg_8]
0x180005b82  cmp     rcx, 7FFFFFFFh
0x180005b89  ja      loc_180005CAE
0x180005b8f  mov     rax, r14
0x180005b92  mov     r8d, ecx
0x180005b95  test    rcx, rcx
0x180005b98  jz      short loc_180005BA9
0x180005b9a  cmp     [rax], bp
0x180005b9d  jz      short loc_180005BA9
0x180005b9f  add     rax, 2
0x180005ba3  sub     rcx, 1
0x180005ba7  jnz     short loc_180005B9A
0x180005ba9  mov     rax, rcx
0x180005bac  mov     ebx, 0C000000Dh
0x180005bb1  neg     rax
0x180005bb4  sbb     edx, edx
0x180005bb6  not     edx
0x180005bb8  and     edx, ebx
0x180005bba  test    rcx, rcx
0x180005bbd  jz      short loc_180005BC4
0x180005bbf  sub     r8, rcx
0x180005bc2  jmp     short loc_180005BC7
0x180005bc4  mov     r8, rbp
0x180005bc7  test    rcx, rcx
0x180005bca  jnz     short loc_180005BD3
0x180005bcc  mov     ebx, edx
0x180005bce  jmp     loc_180005CB3
0x180005bd3  lea     rsi, [r8+1]
0x180005bd7  cmp     rsi, r8
0x180005bda  jb      loc_180005CA0
0x180005be0  mov     rdx, rsi
0x180005be3  lea     rcx, [rsp+68h+arg_18]
0x180005beb  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x180005bf0  mov     rdx, [rax]
0x180005bf3  mov     [rax], rbp
0x180005bf6  mov     rcx, [r15]; void *
0x180005bf9  mov     [r15], rdx
0x180005bfc  test    rcx, rcx
0x180005bff  jz      short loc_180005C06
0x180005c01  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180005c06  mov     rcx, [rsp+68h+arg_18]; void *
0x180005c0e  test    rcx, rcx
0x180005c11  jz      short loc_180005C18
0x180005c13  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180005c18  mov     rdx, [r15]
0x180005c1b  test    rdx, rdx
0x180005c1e  jz      short loc_180005C85
0x180005c20  test    rsi, rsi
0x180005c23  jz      short loc_180005C7C
0x180005c25  cmp     rsi, 7FFFFFFFh
0x180005c2c  ja      short loc_180005C79
0x180005c2e  mov     eax, 7FFFFFFEh
0x180005c33  test    rax, rax
0x180005c36  jz      short loc_180005C55
0x180005c38  movzx   ecx, word ptr [r14]
0x180005c3c  test    cx, cx
0x180005c3f  jz      short loc_180005C55
0x180005c41  mov     [rdx], cx
0x180005c44  add     r14, 2
0x180005c48  add     rdx, 2
0x180005c4c  dec     rax
0x180005c4f  sub     rsi, 1
0x180005c53  jnz     short loc_180005C33
0x180005c55  mov     rax, rsi
0x180005c58  lea     rcx, [rdx-2]
0x180005c5c  neg     rax
0x180005c5f  sbb     ebx, ebx
0x180005c61  not     ebx
0x180005c63  and     ebx, 80000005h
0x180005c69  test    rsi, rsi
0x180005c6c  cmovnz  rcx, rdx
0x180005c70  mov     [rcx], bp
0x180005c73  jz      short loc_180005C7C
0x180005c75  mov     ebx, ebp
0x180005c77  jmp     short loc_180005CCA
0x180005c79  mov     [rdx], bp
0x180005c7c  lea     r8, aWerdiagFailedC_4; "WERDIAG: Failed copying string. NTSTATU"...
0x180005c83  jmp     short loc_180005CBA
0x180005c85  lea     r8, aWerdiagOutOfRe; "WERDIAG: Out of resources allocating me"...
0x180005c8c  xor     edx, edx; Level
0x180005c8e  mov     ecx, 96h; ComponentId
0x180005c93  call    cs:__imp_DbgPrintEx
0x180005c99  mov     ebx, 0C000009Ah
0x180005c9e  jmp     short loc_180005CCA
0x180005ca0  mov     ebx, 0C0000095h
0x180005ca5  lea     r8, aWerdiagRtlsize; "WERDIAG: RtlSizeTAdd failed. NTSTATUS: "...
0x180005cac  jmp     short loc_180005CBA
0x180005cae  mov     ebx, 0C000000Dh
0x180005cb3  lea     r8, aWerdiagFailedD_0; "WERDIAG: Failed determining string buff"...
0x180005cba  mov     r9d, ebx
0x180005cbd  xor     edx, edx; Level
0x180005cbf  mov     ecx, 96h; ComponentId
0x180005cc4  call    cs:__imp_DbgPrintEx
0x180005cca  mov     rcx, rdi; Block
0x180005ccd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005cd2  jmp     short loc_180005CED
0x180005cd4  lea     r8, aWerdiagOutOfRe_0; "WERDIAG: Out of resources allocating me"...
0x180005cdb  xor     edx, edx; Level
0x180005cdd  mov     ecx, 96h; ComponentId
0x180005ce2  call    cs:__imp_DbgPrintEx
0x180005ce8  mov     ebx, 0C000009Ah
0x180005ced  mov     eax, ebx
0x180005cef  jmp     short loc_180005D0A
0x180005cf1  lea     r8, aWerdiagInvalid_3; "WERDIAG: Invalid parameters\n"
0x180005cf8  xor     edx, edx; Level
0x180005cfa  mov     ecx, 96h; ComponentId
0x180005cff  call    cs:__imp_DbgPrintEx
0x180005d05  mov     eax, 0C000000Dh
0x180005d0a  mov     rbx, [rsp+68h+arg_0]
0x180005d0f  add     rsp, 40h
0x180005d13  pop     r15
0x180005d15  pop     r14
0x180005d17  pop     rdi
0x180005d18  pop     rsi
0x180005d19  pop     rbp
0x180005d1a  retn
```
