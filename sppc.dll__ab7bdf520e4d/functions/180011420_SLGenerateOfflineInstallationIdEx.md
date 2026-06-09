# SLGenerateOfflineInstallationIdEx

- ea: `0x180011420`
- end: `0x1800115da`
- name: `SLGenerateOfflineInstallationIdEx`
- size: `442`
- prototype: `HRESULT __stdcall(HSLC hSLC, const SLID *pProductSkuId, const SL_ACTIVATION_INFO_HEADER *pActivationInfo, PWSTR *ppwszInstallationId)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x1800113e0`

## callees

- `0x180001ec0`
- `0x180002bf0`
- `0x180003410`
- `0x1800044dc`
- `0x180004f44`
- `0x180004f80`
- `0x180005208`
- `0x18000532c`
- `0x180006844`
- `0x180008a74`
- `0x18000a8d0`
- `0x18000f144`
- `0x180011420`

## pseudocode

```c
HRESULT __stdcall SLGenerateOfflineInstallationIdEx(
        HSLC hSLC,
        const SLID *pProductSkuId,
        const SL_ACTIVATION_INFO_HEADER *pActivationInfo,
        PWSTR *ppwszInstallationId)
{
  __int64 v8; // rcx
  unsigned int v9; // ebx
  int v10; // eax
  bool v11; // zf
  __int64 v12; // rdx
  int v14; // eax
  WCHAR *v15; // [rsp+30h] [rbp-30h] BYREF
  __int64 v16[2]; // [rsp+38h] [rbp-28h] BYREF
  __int128 v17; // [rsp+48h] [rbp-18h] BYREF
  int v18; // [rsp+80h] [rbp+20h] BYREF

  v18 = 0;
  v17 = 0;
  sub_180003410(byte_1800190A8, &dword_18001E754);
  v15 = 0;
  v16[0] = (__int64)&v17 + 8;
  v16[1] = (__int64)&v17;
  if ( !hSLC || !pProductSkuId || !ppwszInstallationId )
    goto LABEL_2;
  v10 = sub_180004F44(v16, 1, pProductSkuId);
  v9 = v10;
  if ( v10 < 0 )
  {
LABEL_7:
    v8 = (unsigned int)v10;
    goto LABEL_3;
  }
  if ( !pActivationInfo )
  {
    v18 = 0;
    v14 = sub_180004F80(v16, 2, &v18);
    v9 = v14;
    if ( v14 < 0 )
    {
      sub_180006844((unsigned int)v14);
      sub_180002BF0(qword_18001A3D8, &dword_18001EDA4);
      goto LABEL_18;
    }
    goto LABEL_15;
  }
  if ( pActivationInfo->cbSize != 24 || pActivationInfo->type != SL_ACTIVATION_TYPE_ACTIVE_DIRECTORY )
    goto LABEL_2;
  v11 = *(_QWORD *)&pActivationInfo[2] == 0;
  v18 = 1;
  if ( v11 )
  {
    v10 = sub_180004F80(v16, 2, &v18);
    v9 = v10;
    if ( v10 < 0 )
      goto LABEL_7;
    v10 = sub_18000F144(v16, 3, *(_QWORD *)&pActivationInfo[1]);
    v9 = v10;
    if ( v10 < 0 )
      goto LABEL_7;
LABEL_15:
    v10 = sub_1800044DC(v16, (__int64)hSLC, 0x16u, 1, 1);
    v9 = v10;
    if ( v10 >= 0 )
    {
      v10 = sub_180008A74(v16, v12, &v15);
      v9 = v10;
      if ( v10 >= 0 )
      {
        *ppwszInstallationId = v15;
        v15 = 0;
        goto LABEL_18;
      }
    }
    goto LABEL_7;
  }
  sub_180001EC0(&dword_18001A22C, byte_18001E348);
LABEL_2:
  v8 = 2147942487LL;
  v9 = -2147024809;
LABEL_3:
  sub_180006844(v8);
LABEL_18:
  sub_18000A8D0(v9);
  sub_18000532C(&v15);
  sub_180005208(v16);
  return v9;
}

```

## disassembly

```asm
0x180011420  mov     [rsp-18h+arg_8], rbx
0x180011425  mov     [rsp-18h+arg_10], rsi
0x18001142a  push    rbp
0x18001142b  push    rdi
0x18001142c  push    r14
0x18001142e  mov     rbp, rsp
0x180011431  sub     rsp, 60h
0x180011435  mov     rbx, rdx
0x180011438  mov     [rbp+arg_0], 0
0x18001143f  mov     r14, rcx
0x180011442  lea     rdx, dword_18001E754
0x180011449  xorps   xmm0, xmm0
0x18001144c  lea     rcx, byte_1800190A8
0x180011453  movdqu  [rbp+var_18], xmm0
0x180011458  mov     rsi, r9
0x18001145b  mov     rdi, r8
0x18001145e  call    sub_180003410
0x180011463  mov     [rbp+var_30], 0
0x18001146b  lea     rax, [rbp+var_18+8]
0x18001146f  mov     [rbp+var_28], rax
0x180011473  lea     rax, [rbp+var_18]
0x180011477  mov     [rbp+var_20], rax
0x18001147b  test    r14, r14
0x18001147e  jnz     short loc_180011491
0x180011480  mov     ecx, 80070057h
0x180011485  mov     ebx, ecx
0x180011487  call    sub_180006844
0x18001148c  jmp     loc_18001156B
0x180011491  test    rbx, rbx
0x180011494  jz      short loc_180011480
0x180011496  test    rsi, rsi
0x180011499  jz      short loc_180011480
0x18001149b  mov     r8, rbx
0x18001149e  lea     rcx, [rbp+var_28]
0x1800114a2  mov     edx, 1
0x1800114a7  call    sub_180004F44
0x1800114ac  mov     ebx, eax
0x1800114ae  test    eax, eax
0x1800114b0  jns     short loc_1800114B6
0x1800114b2  mov     ecx, eax
0x1800114b4  jmp     short loc_180011487
0x1800114b6  test    rdi, rdi
0x1800114b9  jz      loc_18001159B
0x1800114bf  cmp     dword ptr [rdi], 18h
0x1800114c2  jnz     short loc_180011480
0x1800114c4  cmp     dword ptr [rdi+4], 1
0x1800114c8  jnz     short loc_180011480
0x1800114ca  cmp     qword ptr [rdi+10h], 0
0x1800114cf  mov     [rbp+arg_0], 1
0x1800114d6  jz      short loc_1800114ED
0x1800114d8  lea     rdx, byte_18001E348
0x1800114df  lea     rcx, dword_18001A22C
0x1800114e6  call    sub_180001EC0
0x1800114eb  jmp     short loc_180011480
0x1800114ed  lea     r8, [rbp+arg_0]
0x1800114f1  mov     edx, 2
0x1800114f6  lea     rcx, [rbp+var_28]
0x1800114fa  call    sub_180004F80
0x1800114ff  mov     ebx, eax
0x180011501  test    eax, eax
0x180011503  js      short loc_1800114B2
0x180011505  mov     r8, [rdi+8]
0x180011509  lea     rcx, [rbp+var_28]
0x18001150d  mov     edx, 3
0x180011512  call    sub_18000F144
0x180011517  mov     ebx, eax
0x180011519  test    eax, eax
0x18001151b  js      short loc_1800114B2
0x18001151d  mov     r9d, 1
0x180011523  mov     [rsp+60h+var_40], 1
0x18001152b  mov     rdx, r14
0x18001152e  lea     rcx, [rbp+var_28]
0x180011532  lea     r8d, [r9+15h]
0x180011536  call    sub_1800044DC
0x18001153b  mov     ebx, eax
0x18001153d  test    eax, eax
0x18001153f  js      loc_1800114B2
0x180011545  lea     r8, [rbp+var_30]
0x180011549  lea     rcx, [rbp+var_28]
0x18001154d  call    sub_180008A74
0x180011552  mov     ebx, eax
0x180011554  test    eax, eax
0x180011556  js      loc_1800114B2
0x18001155c  mov     rax, [rbp+var_30]
0x180011560  mov     [rsi], rax
0x180011563  mov     [rbp+var_30], 0
0x18001156b  mov     ecx, ebx
0x18001156d  call    sub_18000A8D0
0x180011572  lea     rcx, [rbp+var_30]
0x180011576  call    sub_18000532C
0x18001157b  lea     rcx, [rbp+var_28]
0x18001157f  call    sub_180005208
0x180011584  lea     r11, [rsp+60h+var_s0]
0x180011589  mov     eax, ebx
0x18001158b  mov     rbx, [r11+28h]
0x18001158f  mov     rsi, [r11+30h]
0x180011593  mov     rsp, r11
0x180011596  pop     r14
0x180011598  pop     rdi
0x180011599  pop     rbp
0x18001159a  retn
0x18001159b  lea     r8, [rbp+arg_0]
0x18001159f  mov     [rbp+arg_0], 0
0x1800115a6  mov     edx, 2
0x1800115ab  lea     rcx, [rbp+var_28]
0x1800115af  call    sub_180004F80
0x1800115b4  mov     ebx, eax
0x1800115b6  test    eax, eax
0x1800115b8  jns     loc_18001151D
0x1800115be  mov     ecx, eax
0x1800115c0  call    sub_180006844
0x1800115c5  lea     rdx, dword_18001EDA4
0x1800115cc  lea     rcx, qword_18001A3D8
0x1800115d3  call    sub_180002BF0
0x1800115d8  jmp     short loc_18001156B
```
