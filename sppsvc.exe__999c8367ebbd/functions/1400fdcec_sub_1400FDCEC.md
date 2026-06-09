# sub_1400FDCEC

- ea: `0x1400fdcec`
- end: `0x1400fe08f`
- name: `sub_1400FDCEC`
- size: `931`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x1400f8a10`

## callees

- `0x140059870`
- `0x1400598ac`
- `0x14006ad34`
- `0x14006adb4`
- `0x14006d1ec`
- `0x14006de60`
- `0x14007cfb4`
- `0x140090cc4`
- `0x1400b489c`
- `0x1400bee78`
- `0x1400fdcec`
- `0x140390f16`
- `0x140390f60`

## import_xrefs

- `KERNEL32!WriteFile` at `0x1400fdf38`
- `KERNEL32!WriteFile` at `0x1400fdfe3`
- `KERNEL32!WriteFile` at `0x1400fe01d`
- `KERNEL32!WriteFile` at `0x1400fdf38`
- `KERNEL32!WriteFile` at `0x1400fdfe3`
- `KERNEL32!WriteFile` at `0x1400fe01d`
- `KERNEL32!GetLastError` at `0x1400fdf42`
- `KERNEL32!GetLastError` at `0x1400fdf42`
- `msvcrt!_wcsicmp` at `0x1400fdd74`
- `msvcrt!_wcsicmp` at `0x1400fdd74`

## string_xrefs

- `0x1400fdd6d`: `msft:spp/migrationencryptor/tokenact/1.0`
- `0x1400fdf67`: `spp:migblob/aesencryptor/tokenact`

## pseudocode

```c
__int64 __fastcall sub_1400FDCEC(__int64 a1, const wchar_t *a2, void *a3)
{
  unsigned int v6; // ebx
  int v7; // ecx
  int v8; // eax
  __int64 v9; // r14
  __int64 (__fastcall *v10)(__int64); // rbx
  __int64 (__fastcall *v11)(__int64, const wchar_t *, void **); // rbx
  __int64 v12; // rdx
  DWORD LastError; // eax
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-D0h] BYREF
  void *v16; // [rsp+38h] [rbp-C8h] BYREF
  int v17; // [rsp+40h] [rbp-C0h] BYREF
  int Buffer; // [rsp+44h] [rbp-BCh] BYREF
  int v19; // [rsp+48h] [rbp-B8h] BYREF
  int v20; // [rsp+4Ch] [rbp-B4h] BYREF
  __int64 v21; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD *v22; // [rsp+58h] [rbp-A8h] BYREF
  __int64 SystemInformation; // [rsp+60h] [rbp-A0h] BYREF
  __int64 *v24; // [rsp+68h] [rbp-98h]
  int *v25; // [rsp+70h] [rbp-90h]
  _BYTE v26[12]; // [rsp+78h] [rbp-88h]
  __int128 v27; // [rsp+84h] [rbp-7Ch]
  _QWORD *v28; // [rsp+94h] [rbp-6Ch]
  _QWORD v29[32]; // [rsp+A0h] [rbp-60h] BYREF

  v22 = 0;
  v17 = 0;
  v21 = 0;
  v16 = 0;
  Buffer = 0;
  memset(v29, 0, 0xFCu);
  NumberOfBytesWritten = 0;
  if ( !a2 || !wcsicmp(L"msft:spp/migrationencryptor/tokenact/1.0", a2) )
  {
    v8 = sub_1400BEE78((BYTE *)(a1 + 16));
    v6 = v8;
    if ( v8 < 0 )
    {
LABEL_7:
      v7 = v8;
      goto LABEL_5;
    }
    SystemInformation = 3;
    v24 = qword_14000DCC0;
    *(_QWORD *)v26 = a1 + 16;
    v25 = &v19;
    *(_DWORD *)&v26[8] = 64;
    *(_QWORD *)&v27 = &v22;
    *((_QWORD *)&v27 + 1) = &v17;
    NtQuerySystemInformation(SystemExtendedProcessInformation|0x80, &SystemInformation, 0x3Cu, 0);
    v6 = v19;
    if ( v19 < 0 )
      goto LABEL_4;
    if ( v17 != 96 )
      goto LABEL_10;
    v8 = sub_1400B489C(L"msft:rm/algorithm/hwid/4.0", 0, &v21);
    v6 = v8;
    if ( v8 < 0 )
      goto LABEL_7;
    v9 = v21;
    v10 = *(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 96LL);
    _guard_check_icall_fptr();
    v8 = v10(v9);
    v6 = v8;
    if ( v8 < 0 )
      goto LABEL_7;
    v11 = *(__int64 (__fastcall **)(__int64, const wchar_t *, void **))(*(_QWORD *)v9 + 56LL);
    _guard_check_icall_fptr();
    v8 = v11(v9, L"SppBindingEnvironmentData", &v16);
    v6 = v8;
    if ( v8 < 0 )
      goto LABEL_7;
    if ( *((_DWORD *)v16 + 2) == 4 && *((_DWORD *)v16 + 6) )
    {
      v12 = *((_QWORD *)v16 + 2);
      *(_DWORD *)v26 = *((_DWORD *)v16 + 6);
      v24 = qword_140009880;
      v25 = &v20;
      *(_QWORD *)&v26[4] = v12;
      v28 = &v29[27];
      SystemInformation = 3;
      LODWORD(v27) = 64;
      *(_QWORD *)((char *)&v27 + 4) = a1 + 16;
      HIDWORD(v27) = 32;
      NtQuerySystemInformation(SystemExtendedProcessInformation|0x80, &SystemInformation, 0x3Cu, 0);
      v6 = v20;
      if ( v20 < 0 )
        goto LABEL_4;
      Buffer = 2;
      if ( !WriteFile(a3, &Buffer, 4u, &NumberOfBytesWritten, 0) )
        goto LABEL_19;
      if ( NumberOfBytesWritten == 4 )
      {
        v8 = sub_140090CC4(v29, 120, L"spp:migblob/aesencryptor/tokenact");
        v6 = v8;
        if ( v8 < 0 )
          goto LABEL_7;
        *(_OWORD *)&v29[15] = *v22;
        *(_OWORD *)&v29[17] = v22[1];
        *(_OWORD *)&v29[19] = v22[2];
        *(_OWORD *)&v29[21] = v22[3];
        *(_OWORD *)&v29[23] = v22[4];
        *(_OWORD *)&v29[25] = v22[5];
        LODWORD(v29[31]) = *((_DWORD *)v16 + 6);
        if ( !WriteFile(a3, v29, 0xFCu, &NumberOfBytesWritten, 0) )
          goto LABEL_19;
        if ( NumberOfBytesWritten == 252 )
        {
          if ( !WriteFile(a3, *((LPCVOID *)v16 + 2), *((_DWORD *)v16 + 6), &NumberOfBytesWritten, 0) )
          {
LABEL_19:
            LastError = GetLastError();
            v8 = sub_14006D1EC(LastError);
            v6 = v8;
            goto LABEL_7;
          }
          if ( NumberOfBytesWritten == *((_DWORD *)v16 + 6) )
          {
            *(_QWORD *)(a1 + 8) = a3;
            goto LABEL_28;
          }
        }
      }
      v7 = -2147467259;
    }
    else
    {
LABEL_10:
      v7 = -2147024883;
    }
    v6 = v7;
    goto LABEL_5;
  }
  v6 = -2147024809;
LABEL_4:
  v7 = v6;
LABEL_5:
  sub_14006DE60(v7);
LABEL_28:
  sub_14007CFB4(v6);
  sub_14006ADB4(&v16);
  sub_14006AD34(&v21);
  sub_14006ADB4((void **)&v22);
  return v6;
}

```

## disassembly

```asm
0x1400fdcec  mov     [rsp-8+arg_18], rbx
0x1400fdcf1  push    rbp
0x1400fdcf2  push    rsi
0x1400fdcf3  push    rdi
0x1400fdcf4  push    r14
0x1400fdcf6  push    r15
0x1400fdcf8  lea     rbp, [rsp-0B0h]
0x1400fdd00  sub     rsp, 1B0h
0x1400fdd07  mov     rax, cs:__security_cookie
0x1400fdd0e  xor     rax, rsp
0x1400fdd11  mov     [rbp+0D0h+var_30], rax
0x1400fdd18  mov     rdi, r8
0x1400fdd1b  mov     [rsp+1D0h+var_178], 0
0x1400fdd24  mov     rbx, rdx
0x1400fdd27  mov     [rsp+1D0h+var_190], 0
0x1400fdd2f  mov     r15, rcx
0x1400fdd32  mov     [rsp+1D0h+var_180], 0
0x1400fdd3b  xor     edx, edx; Val
0x1400fdd3d  mov     [rsp+1D0h+var_198], 0
0x1400fdd46  mov     r8d, 0FCh; Size
0x1400fdd4c  mov     [rsp+1D0h+Buffer], 0
0x1400fdd54  lea     rcx, [rbp+0D0h+var_130]; void *
0x1400fdd58  call    memset
0x1400fdd5d  mov     [rsp+1D0h+NumberOfBytesWritten], 0
0x1400fdd65  test    rbx, rbx
0x1400fdd68  jz      short loc_1400FDD8F
0x1400fdd6a  mov     rdx, rbx; String2
0x1400fdd6d  lea     rcx, aMsftSppMigrati; "msft:spp/migrationencryptor/tokenact/1."...
0x1400fdd74  call    cs:_wcsicmp
0x1400fdd7a  test    eax, eax
0x1400fdd7c  jz      short loc_1400FDD8F
0x1400fdd7e  mov     ebx, 80070057h
0x1400fdd83  mov     ecx, ebx
0x1400fdd85  call    sub_14006DE60
0x1400fdd8a  jmp     loc_1400FE041
0x1400fdd8f  lea     rsi, [r15+10h]
0x1400fdd93  mov     edx, 40h ; '@'
0x1400fdd98  mov     rcx, rsi; pbBuffer
0x1400fdd9b  call    sub_1400BEE78
0x1400fdda0  mov     ebx, eax
0x1400fdda2  test    eax, eax
0x1400fdda4  jns     short loc_1400FDDAA
0x1400fdda6  mov     ecx, eax
0x1400fdda8  jmp     short loc_1400FDD85
0x1400fddaa  lea     rax, qword_14000DCC0
0x1400fddb1  mov     [rsp+1D0h+SystemInformation], 3
0x1400fddba  mov     [rsp+1D0h+var_168], rax
0x1400fddbf  lea     rdx, [rsp+1D0h+SystemInformation]; SystemInformation
0x1400fddc4  lea     rax, [rsp+1D0h+var_188]
0x1400fddc9  mov     [rsp+1D0h+var_158], rsi
0x1400fddce  mov     [rsp+1D0h+var_160], rax
0x1400fddd3  xor     r9d, r9d; ReturnLength
0x1400fddd6  lea     rax, [rsp+1D0h+var_178]
0x1400fdddb  mov     [rbp+0D0h+var_150], 40h ; '@'
0x1400fdde2  mov     [rbp+0D0h+var_14C], rax
0x1400fdde6  lea     rax, [rsp+1D0h+var_190]
0x1400fddeb  mov     [rbp+0D0h+var_144], rax
0x1400fddef  lea     r8d, [r9+3Ch]; SystemInformationLength
0x1400fddf3  lea     ecx, [r8+7Dh]; SystemInformationClass
0x1400fddf7  call    NtQuerySystemInformation
0x1400fddfc  mov     ebx, [rsp+1D0h+var_188]
0x1400fde00  test    ebx, ebx
0x1400fde02  js      loc_1400FDD83
0x1400fde08  cmp     [rsp+1D0h+var_190], 60h ; '`'
0x1400fde0d  jz      short loc_1400FDE1B
0x1400fde0f  mov     ecx, 8007000Dh
0x1400fde14  mov     ebx, ecx
0x1400fde16  jmp     loc_1400FDD85
0x1400fde1b  lea     r8, [rsp+1D0h+var_180]
0x1400fde20  xor     edx, edx
0x1400fde22  lea     rcx, aMsftRmAlgorith_0; "msft:rm/algorithm/hwid/4.0"
0x1400fde29  call    sub_1400B489C
0x1400fde2e  mov     ebx, eax
0x1400fde30  test    eax, eax
0x1400fde32  js      loc_1400FDDA6
0x1400fde38  mov     r14, [rsp+1D0h+var_180]
0x1400fde3d  mov     rax, [r14]
0x1400fde40  mov     rbx, [rax+60h]
0x1400fde44  mov     rax, cs:__guard_check_icall_fptr
0x1400fde4b  mov     rcx, rbx
0x1400fde4e  call    rax ; _guard_check_icall_nop
0x1400fde50  mov     rax, rbx
0x1400fde53  mov     rcx, r14
0x1400fde56  call    rax
0x1400fde58  mov     ebx, eax
0x1400fde5a  test    eax, eax
0x1400fde5c  js      loc_1400FDDA6
0x1400fde62  mov     rax, [r14]
0x1400fde65  mov     rbx, [rax+38h]
0x1400fde69  mov     rax, cs:__guard_check_icall_fptr
0x1400fde70  mov     rcx, rbx
0x1400fde73  call    rax ; _guard_check_icall_nop
0x1400fde75  mov     rax, rbx
0x1400fde78  lea     r8, [rsp+1D0h+var_198]
0x1400fde7d  lea     rdx, aSppbindingenvi; "SppBindingEnvironmentData"
0x1400fde84  mov     rcx, r14
0x1400fde87  call    rax
0x1400fde89  mov     ebx, eax
0x1400fde8b  test    eax, eax
0x1400fde8d  js      loc_1400FDDA6
0x1400fde93  mov     rax, [rsp+1D0h+var_198]
0x1400fde98  cmp     dword ptr [rax+8], 4
0x1400fde9c  jnz     loc_1400FDE0F
0x1400fdea2  mov     ecx, [rax+18h]
0x1400fdea5  test    ecx, ecx
0x1400fdea7  jz      loc_1400FDE0F
0x1400fdead  mov     rdx, [rax+10h]
0x1400fdeb1  xor     r9d, r9d; ReturnLength
0x1400fdeb4  lea     rax, qword_140009880
0x1400fdebb  mov     dword ptr [rsp+1D0h+var_158], ecx
0x1400fdebf  mov     [rsp+1D0h+var_168], rax
0x1400fdec4  lea     rax, [rsp+1D0h+var_184]
0x1400fdec9  mov     [rsp+1D0h+var_160], rax
0x1400fdece  lea     rax, [rbp+0D0h+var_58]
0x1400fded2  lea     r8d, [r9+3Ch]; SystemInformationLength
0x1400fded6  mov     [rsp+1D0h+var_158+4], rdx
0x1400fdedb  lea     rdx, [rsp+1D0h+SystemInformation]; SystemInformation
0x1400fdee0  mov     [rbp+0D0h+var_13C], rax
0x1400fdee4  lea     ecx, [r8+7Dh]; SystemInformationClass
0x1400fdee8  mov     [rsp+1D0h+SystemInformation], 3
0x1400fdef1  mov     dword ptr [rbp+0D0h+var_14C], 40h ; '@'
0x1400fdef8  mov     [rbp+0D0h+var_14C+4], rsi
0x1400fdefc  mov     dword ptr [rbp+0D0h+var_144+4], 20h ; ' '
0x1400fdf03  call    NtQuerySystemInformation
0x1400fdf08  mov     ebx, [rsp+1D0h+var_184]
0x1400fdf0c  test    ebx, ebx
0x1400fdf0e  js      loc_1400FDD83
0x1400fdf14  lea     r9, [rsp+1D0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1400fdf19  mov     [rsp+1D0h+Buffer], 2
0x1400fdf21  mov     r8d, 4; nNumberOfBytesToWrite
0x1400fdf27  mov     [rsp+1D0h+lpOverlapped], 0; lpOverlapped
0x1400fdf30  lea     rdx, [rsp+1D0h+Buffer]; lpBuffer
0x1400fdf35  mov     rcx, rdi; hFile
0x1400fdf38  call    cs:WriteFile
0x1400fdf3e  test    eax, eax
0x1400fdf40  jnz     short loc_1400FDF56
0x1400fdf42  call    cs:GetLastError
0x1400fdf48  mov     ecx, eax
0x1400fdf4a  call    sub_14006D1EC
0x1400fdf4f  mov     ebx, eax
0x1400fdf51  jmp     loc_1400FDDA6
0x1400fdf56  cmp     [rsp+1D0h+NumberOfBytesWritten], 4
0x1400fdf5b  jz      short loc_1400FDF67
0x1400fdf5d  mov     ecx, 80004005h
0x1400fdf62  jmp     loc_1400FDE14
0x1400fdf67  lea     r8, aSppMigblobAese; "spp:migblob/aesencryptor/tokenact"
0x1400fdf6e  mov     edx, 78h ; 'x'
0x1400fdf73  lea     rcx, [rbp+0D0h+var_130]
0x1400fdf77  call    sub_140090CC4
0x1400fdf7c  mov     ebx, eax
0x1400fdf7e  test    eax, eax
0x1400fdf80  js      loc_1400FDDA6
0x1400fdf86  mov     rax, [rsp+1D0h+var_178]
0x1400fdf8b  lea     r9, [rsp+1D0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1400fdf90  mov     r8d, 0FCh; nNumberOfBytesToWrite
0x1400fdf96  mov     [rsp+1D0h+lpOverlapped], 0; lpOverlapped
0x1400fdf9f  lea     rdx, [rbp+0D0h+var_130]; lpBuffer
0x1400fdfa3  movups  xmm0, xmmword ptr [rax]
0x1400fdfa6  movups  [rbp+0D0h+var_B8], xmm0
0x1400fdfaa  movups  xmm1, xmmword ptr [rax+10h]
0x1400fdfae  movups  [rbp+0D0h+var_A8], xmm1
0x1400fdfb2  movups  xmm0, xmmword ptr [rax+20h]
0x1400fdfb6  movups  [rbp+0D0h+var_98], xmm0
0x1400fdfba  movups  xmm1, xmmword ptr [rax+30h]
0x1400fdfbe  movups  [rbp+0D0h+var_88], xmm1
0x1400fdfc2  movups  xmm0, xmmword ptr [rax+40h]
0x1400fdfc6  movups  [rbp+0D0h+var_78], xmm0
0x1400fdfca  movups  xmm1, xmmword ptr [rax+50h]
0x1400fdfce  mov     rax, [rsp+1D0h+var_198]
0x1400fdfd3  movups  [rbp+0D0h+var_68], xmm1
0x1400fdfd7  mov     ecx, [rax+18h]
0x1400fdfda  mov     [rbp+0D0h+var_38], ecx
0x1400fdfe0  mov     rcx, rdi; hFile
0x1400fdfe3  call    cs:WriteFile
0x1400fdfe9  test    eax, eax
0x1400fdfeb  jz      loc_1400FDF42
0x1400fdff1  cmp     [rsp+1D0h+NumberOfBytesWritten], 0FCh
0x1400fdff9  jnz     loc_1400FDF5D
0x1400fdfff  mov     rdx, [rsp+1D0h+var_198]
0x1400fe004  lea     r9, [rsp+1D0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1400fe009  mov     rcx, rdi; hFile
0x1400fe00c  mov     [rsp+1D0h+lpOverlapped], 0; lpOverlapped
0x1400fe015  mov     r8d, [rdx+18h]; nNumberOfBytesToWrite
0x1400fe019  mov     rdx, [rdx+10h]; lpBuffer
0x1400fe01d  call    cs:WriteFile
0x1400fe023  test    eax, eax
0x1400fe025  jz      loc_1400FDF42
0x1400fe02b  mov     rax, [rsp+1D0h+var_198]
0x1400fe030  mov     ecx, [rax+18h]
0x1400fe033  cmp     [rsp+1D0h+NumberOfBytesWritten], ecx
0x1400fe037  jnz     loc_1400FDF5D
0x1400fe03d  mov     [r15+8], rdi
0x1400fe041  mov     ecx, ebx
0x1400fe043  call    sub_14007CFB4
0x1400fe048  lea     rcx, [rsp+1D0h+var_198]
0x1400fe04d  call    sub_14006ADB4
0x1400fe052  lea     rcx, [rsp+1D0h+var_180]
0x1400fe057  call    sub_14006AD34
0x1400fe05c  lea     rcx, [rsp+1D0h+var_178]
0x1400fe061  call    sub_14006ADB4
0x1400fe066  mov     eax, ebx
0x1400fe068  mov     rcx, [rbp+0D0h+var_30]
0x1400fe06f  xor     rcx, rsp; StackCookie
0x1400fe072  call    __security_check_cookie
0x1400fe077  mov     rbx, [rsp+1D0h+arg_18]
0x1400fe07f  add     rsp, 1B0h
0x1400fe086  pop     r15
0x1400fe088  pop     r14
0x1400fe08a  pop     rdi
0x1400fe08b  pop     rsi
0x1400fe08c  pop     rbp
0x1400fe08d  retn
```
