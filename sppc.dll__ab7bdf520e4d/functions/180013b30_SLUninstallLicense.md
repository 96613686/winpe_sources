# SLUninstallLicense

- ea: `0x180013b30`
- end: `0x180013c1a`
- name: `SLUninstallLicense`
- size: `234`
- prototype: `HRESULT __stdcall(HSLC hSLC, const SLID *pLicenseFileId)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update`

## callees

- `0x180001a90`
- `0x1800028f0`
- `0x180003030`
- `0x1800044dc`
- `0x180004f44`
- `0x180005208`
- `0x180006844`
- `0x18000a8d0`
- `0x180013b30`

## pseudocode

```c
HRESULT __stdcall SLUninstallLicense(HSLC hSLC, const SLID *pLicenseFileId)
{
  HRESULT v3; // ebx
  __int64 v4; // rcx
  int v5; // eax
  __int64 v7[2]; // [rsp+30h] [rbp-28h] BYREF
  __int128 v8; // [rsp+40h] [rbp-18h] BYREF

  v8 = 0;
  v7[0] = (__int64)&v8 + 8;
  v7[1] = (__int64)&v8;
  if ( !hSLC )
  {
    v3 = -2147024809;
    sub_180006844(2147942487LL);
    sub_1800028F0(qword_180019740, qword_18001E908);
    goto LABEL_10;
  }
  if ( !pLicenseFileId )
  {
    v4 = 2147942487LL;
    v3 = -2147024809;
LABEL_5:
    sub_180006844(v4);
    goto LABEL_10;
  }
  v3 = sub_180004F44(v7, 1, pLicenseFileId);
  sub_180003030(byte_1800187B8, byte_18001E9B8);
  if ( v3 < 0 )
  {
    v4 = (unsigned int)v3;
    goto LABEL_5;
  }
  v5 = sub_1800044DC(v7, (__int64)hSLC, 1u, 0, 1);
  v3 = v5;
  if ( v5 < 0 )
  {
    sub_180006844((unsigned int)v5);
    sub_180001A90(byte_180018FC8, &dword_18001E5E4);
  }
LABEL_10:
  sub_18000A8D0((unsigned int)v3);
  sub_180005208(v7);
  return v3;
}

```

## disassembly

```asm
0x180013b30  mov     r11, rsp
0x180013b33  mov     [r11+8], rbx
0x180013b37  push    rdi
0x180013b38  sub     rsp, 50h
0x180013b3c  lea     rax, [r11-10h]
0x180013b40  xorps   xmm0, xmm0
0x180013b43  mov     rdi, rcx
0x180013b46  movdqu  [rsp+58h+var_18], xmm0
0x180013b4c  mov     [r11-28h], rax
0x180013b50  lea     rax, [r11-18h]
0x180013b54  mov     [r11-20h], rax
0x180013b58  test    rcx, rcx
0x180013b5b  jnz     short loc_180013B7E
0x180013b5d  mov     ecx, 80070057h
0x180013b62  mov     ebx, ecx
0x180013b64  call    sub_180006844
0x180013b69  lea     rdx, qword_18001E908
0x180013b70  lea     rcx, qword_180019740
0x180013b77  call    sub_1800028F0
0x180013b7c  jmp     short loc_180013BFC
0x180013b7e  test    rdx, rdx
0x180013b81  jnz     short loc_180013B91
0x180013b83  mov     ecx, 80070057h
0x180013b88  mov     ebx, ecx
0x180013b8a  call    sub_180006844
0x180013b8f  jmp     short loc_180013BFC
0x180013b91  mov     r8, rdx
0x180013b94  lea     rcx, [rsp+58h+var_28]
0x180013b99  mov     edx, 1
0x180013b9e  call    sub_180004F44
0x180013ba3  lea     rdx, byte_18001E9B8
0x180013baa  mov     ebx, eax
0x180013bac  lea     rcx, byte_1800187B8
0x180013bb3  call    sub_180003030
0x180013bb8  test    ebx, ebx
0x180013bba  jns     short loc_180013BC0
0x180013bbc  mov     ecx, ebx
0x180013bbe  jmp     short loc_180013B8A
0x180013bc0  xor     r9d, r9d
0x180013bc3  mov     [rsp+58h+var_38], 1
0x180013bcb  mov     rdx, rdi
0x180013bce  lea     rcx, [rsp+58h+var_28]
0x180013bd3  lea     r8d, [r9+1]
0x180013bd7  call    sub_1800044DC
0x180013bdc  mov     ebx, eax
0x180013bde  test    eax, eax
0x180013be0  jns     short loc_180013BFC
0x180013be2  mov     ecx, eax
0x180013be4  call    sub_180006844
0x180013be9  lea     rdx, dword_18001E5E4
0x180013bf0  lea     rcx, byte_180018FC8
0x180013bf7  call    sub_180001A90
0x180013bfc  mov     ecx, ebx
0x180013bfe  call    sub_18000A8D0
0x180013c03  lea     rcx, [rsp+58h+var_28]
0x180013c08  call    sub_180005208
0x180013c0d  mov     eax, ebx
0x180013c0f  mov     rbx, [rsp+58h+arg_0]
0x180013c14  add     rsp, 50h
0x180013c18  pop     rdi
0x180013c19  retn
```
