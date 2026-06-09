# sub_1400FDBB0

- ea: `0x1400fdbb0`
- end: `0x1400fdce5`
- name: `sub_1400FDBB0`
- size: `309`
- prototype: `__int64 __fastcall(__int64, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x1400f8948`

## callees

- `0x14006ad88`
- `0x14006adb4`
- `0x14006b430`
- `0x14006d1ec`
- `0x14006de60`
- `0x14007cfb4`
- `0x1400fdbb0`
- `0x140100cd4`
- `0x140100dd4`

## import_xrefs

- `KERNEL32!ReadFile` at `0x1400fdc09`
- `KERNEL32!ReadFile` at `0x1400fdc09`
- `KERNEL32!GetLastError` at `0x1400fdc13`
- `KERNEL32!GetLastError` at `0x1400fdc13`

## pseudocode

```c
__int64 __fastcall sub_1400FDBB0(__int64 a1, void *a2)
{
  __int64 v2; // r12
  int v5; // r15d
  __int64 v6; // rcx
  DWORD LastError; // eax
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rcx
  int v11; // r14d
  int v13; // [rsp+30h] [rbp-20h] BYREF
  int v14; // [rsp+34h] [rbp-1Ch] BYREF
  __int64 v15; // [rsp+38h] [rbp-18h] BYREF
  __int64 v16; // [rsp+40h] [rbp-10h] BYREF
  int Buffer; // [rsp+90h] [rbp+40h] BYREF
  DWORD NumberOfBytesRead; // [rsp+98h] [rbp+48h] BYREF

  v2 = 0;
  Buffer = 0;
  v16 = 0;
  v15 = 0;
  v5 = 0;
  v14 = 0;
  v13 = 0;
  NumberOfBytesRead = 0;
  if ( ReadFile(a2, &Buffer, 4u, &NumberOfBytesRead, 0) )
  {
    if ( NumberOfBytesRead != 4 )
    {
LABEL_6:
      v10 = 2147942413LL;
      v9 = -2147024883;
      goto LABEL_4;
    }
    if ( Buffer == 1 )
    {
      v8 = sub_140100CD4(v6, a2);
      v9 = v8;
      if ( v8 < 0 )
        goto LABEL_3;
      v11 = 1;
    }
    else
    {
      if ( Buffer != 2 )
        goto LABEL_6;
      v8 = sub_140100DD4(v6, a2, &v13, &v15, &v14);
      v9 = v8;
      if ( v8 < 0 )
        goto LABEL_3;
      v2 = v15;
      v5 = v13;
      v11 = v14;
    }
    *(_QWORD *)(a1 + 8) = a2;
    v15 = 0;
    sub_14006B430(a1 + 24, v2);
    *(_DWORD *)a1 = Buffer;
    *(_DWORD *)(a1 + 32) = v5;
    *(_DWORD *)(a1 + 16) = v11;
    goto LABEL_14;
  }
  LastError = GetLastError();
  v8 = sub_14006D1EC(LastError);
  v9 = v8;
LABEL_3:
  v10 = (unsigned int)v8;
LABEL_4:
  sub_14006DE60(v10);
LABEL_14:
  sub_14007CFB4(v9);
  sub_14006ADB4(&v15);
  sub_14006AD88(&v16);
  return v9;
}

```

## disassembly

```asm
0x1400fdbb0  mov     [rsp-28h+arg_0], rbx
0x1400fdbb5  mov     [rsp-28h+arg_8], rsi
0x1400fdbba  push    rbp
0x1400fdbbb  push    rdi
0x1400fdbbc  push    r12
0x1400fdbbe  push    r14
0x1400fdbc0  push    r15
0x1400fdbc2  mov     rbp, rsp
0x1400fdbc5  sub     rsp, 50h
0x1400fdbc9  xor     r12d, r12d
0x1400fdbcc  mov     [rbp+Buffer], 0
0x1400fdbd3  mov     rsi, rdx
0x1400fdbd6  mov     [rbp+var_10], 0
0x1400fdbde  mov     rdi, rcx
0x1400fdbe1  mov     [rbp+var_18], r12
0x1400fdbe5  xor     r15d, r15d
0x1400fdbe8  mov     [rbp+var_1C], r12d
0x1400fdbec  lea     r8d, [r12+4]; nNumberOfBytesToRead
0x1400fdbf1  mov     [rbp+var_20], r15d
0x1400fdbf5  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1400fdbf9  mov     [rbp+NumberOfBytesRead], r12d
0x1400fdbfd  lea     rdx, [rbp+Buffer]; lpBuffer
0x1400fdc01  mov     [rsp+50h+lpOverlapped], r12; lpOverlapped
0x1400fdc06  mov     rcx, rsi; hFile
0x1400fdc09  call    cs:ReadFile
0x1400fdc0f  test    eax, eax
0x1400fdc11  jnz     short loc_1400FDC2E
0x1400fdc13  call    cs:GetLastError
0x1400fdc19  mov     ecx, eax
0x1400fdc1b  call    sub_14006D1EC
0x1400fdc20  mov     ebx, eax
0x1400fdc22  mov     ecx, eax
0x1400fdc24  call    sub_14006DE60
0x1400fdc29  jmp     loc_1400FDCB0
0x1400fdc2e  cmp     [rbp+NumberOfBytesRead], 4
0x1400fdc32  jz      short loc_1400FDC3D
0x1400fdc34  mov     ecx, 8007000Dh
0x1400fdc39  mov     ebx, ecx
0x1400fdc3b  jmp     short loc_1400FDC24
0x1400fdc3d  mov     eax, [rbp+Buffer]
0x1400fdc40  sub     eax, 1
0x1400fdc43  jz      short loc_1400FDC77
0x1400fdc45  cmp     eax, 1
0x1400fdc48  jnz     short loc_1400FDC34
0x1400fdc4a  lea     rax, [rbp+var_1C]
0x1400fdc4e  mov     rdx, rsi
0x1400fdc51  lea     r9, [rbp+var_18]
0x1400fdc55  mov     [rsp+50h+lpOverlapped], rax
0x1400fdc5a  lea     r8, [rbp+var_20]
0x1400fdc5e  call    sub_140100DD4
0x1400fdc63  mov     ebx, eax
0x1400fdc65  test    eax, eax
0x1400fdc67  js      short loc_1400FDC22
0x1400fdc69  mov     r12, [rbp+var_18]
0x1400fdc6d  mov     r15d, [rbp+var_20]
0x1400fdc71  mov     r14d, [rbp+var_1C]
0x1400fdc75  jmp     short loc_1400FDC8B
0x1400fdc77  mov     rdx, rsi
0x1400fdc7a  call    sub_140100CD4
0x1400fdc7f  mov     ebx, eax
0x1400fdc81  test    eax, eax
0x1400fdc83  js      short loc_1400FDC22
0x1400fdc85  mov     r14d, 1
0x1400fdc8b  lea     rcx, [rdi+18h]
0x1400fdc8f  mov     [rdi+8], rsi
0x1400fdc93  mov     rdx, r12
0x1400fdc96  mov     [rbp+var_18], 0
0x1400fdc9e  call    sub_14006B430
0x1400fdca3  mov     eax, [rbp+Buffer]
0x1400fdca6  mov     [rdi], eax
0x1400fdca8  mov     [rdi+20h], r15d
0x1400fdcac  mov     [rdi+10h], r14d
0x1400fdcb0  mov     ecx, ebx
0x1400fdcb2  call    sub_14007CFB4
0x1400fdcb7  lea     rcx, [rbp+var_18]
0x1400fdcbb  call    sub_14006ADB4
0x1400fdcc0  lea     rcx, [rbp+var_10]
0x1400fdcc4  call    sub_14006AD88
0x1400fdcc9  lea     r11, [rsp+50h+var_s0]
0x1400fdcce  mov     eax, ebx
0x1400fdcd0  mov     rbx, [r11+30h]
0x1400fdcd4  mov     rsi, [r11+38h]
0x1400fdcd8  mov     rsp, r11
0x1400fdcdb  pop     r15
0x1400fdcdd  pop     r14
0x1400fdcdf  pop     r12
0x1400fdce1  pop     rdi
0x1400fdce2  pop     rbp
0x1400fdce3  retn
```
