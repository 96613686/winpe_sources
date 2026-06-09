# FreeVolumeRestoreEventInfo

- ea: `0x140057a4c`
- end: `0x140057bf2`
- name: `FreeVolumeRestoreEventInfo`
- size: `422`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140059750`

## callees

- `0x140057a4c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x140057a7e`
- `ole32!CoTaskMemFree` at `0x140057a96`
- `ole32!CoTaskMemFree` at `0x140057abd`
- `ole32!CoTaskMemFree` at `0x140057ad5`
- `ole32!CoTaskMemFree` at `0x140057ae8`
- `ole32!CoTaskMemFree` at `0x140057afe`
- `ole32!CoTaskMemFree` at `0x140057b17`
- `ole32!CoTaskMemFree` at `0x140057b30`
- `ole32!CoTaskMemFree` at `0x140057b49`
- `ole32!CoTaskMemFree` at `0x140057b5f`
- `ole32!CoTaskMemFree` at `0x140057b72`
- `ole32!CoTaskMemFree` at `0x140057b85`
- `ole32!CoTaskMemFree` at `0x140057b98`
- `ole32!CoTaskMemFree` at `0x140057bab`
- `ole32!CoTaskMemFree` at `0x140057bc1`
- `ole32!CoTaskMemFree` at `0x140057bda`
- `ole32!CoTaskMemFree` at `0x140057a7e`
- `ole32!CoTaskMemFree` at `0x140057a96`
- `ole32!CoTaskMemFree` at `0x140057abd`
- `ole32!CoTaskMemFree` at `0x140057ad5`
- `ole32!CoTaskMemFree` at `0x140057ae8`
- `ole32!CoTaskMemFree` at `0x140057afe`
- `ole32!CoTaskMemFree` at `0x140057b17`
- `ole32!CoTaskMemFree` at `0x140057b30`
- `ole32!CoTaskMemFree` at `0x140057b49`
- `ole32!CoTaskMemFree` at `0x140057b5f`
- `ole32!CoTaskMemFree` at `0x140057b72`
- `ole32!CoTaskMemFree` at `0x140057b85`
- `ole32!CoTaskMemFree` at `0x140057b98`
- `ole32!CoTaskMemFree` at `0x140057bab`
- `ole32!CoTaskMemFree` at `0x140057bc1`
- `ole32!CoTaskMemFree` at `0x140057bda`

## pseudocode

```c
void __fastcall FreeVolumeRestoreEventInfo(__int64 a1)
{
  unsigned int *v1; // rdi
  unsigned int i; // esi
  void *v4; // rcx
  unsigned int j; // esi
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  void *v15; // rcx
  void *v16; // rcx
  void *v17; // rcx
  void *v18; // rcx

  v1 = (unsigned int *)(a1 + 64);
  if ( *(_QWORD *)(a1 + 72) )
  {
    for ( i = 0; i < *v1; ++i )
    {
      v4 = *(void **)(*(_QWORD *)(a1 + 72) + 8LL * i);
      if ( v4 )
      {
        CoTaskMemFree(v4);
        *(_QWORD *)(*(_QWORD *)(a1 + 72) + 8LL * i) = 0;
      }
    }
    CoTaskMemFree(*(LPVOID *)(a1 + 72));
    *(_QWORD *)(a1 + 72) = 0;
  }
  if ( *(_QWORD *)(a1 + 80) )
  {
    for ( j = 0; j < *v1; ++j )
    {
      v6 = *(void **)(*(_QWORD *)(a1 + 80) + 8LL * j);
      if ( v6 )
      {
        CoTaskMemFree(v6);
        *(_QWORD *)(*(_QWORD *)(a1 + 80) + 8LL * j) = 0;
      }
    }
    CoTaskMemFree(*(LPVOID *)(a1 + 80));
    *(_QWORD *)(a1 + 80) = 0;
  }
  v7 = *(void **)(a1 + 88);
  if ( v7 )
  {
    CoTaskMemFree(v7);
    *(_QWORD *)(a1 + 88) = 0;
  }
  v8 = *(void **)(a1 + 128);
  if ( v8 )
  {
    CoTaskMemFree(v8);
    *(_QWORD *)(a1 + 128) = 0;
  }
  v9 = *(void **)(a1 + 136);
  if ( v9 )
  {
    CoTaskMemFree(v9);
    *(_QWORD *)(a1 + 136) = 0;
  }
  v10 = *(void **)(a1 + 144);
  if ( v10 )
  {
    CoTaskMemFree(v10);
    *(_QWORD *)(a1 + 144) = 0;
  }
  v11 = *(void **)(a1 + 152);
  if ( v11 )
  {
    CoTaskMemFree(v11);
    *(_QWORD *)(a1 + 152) = 0;
  }
  v12 = *(void **)(a1 + 56);
  if ( v12 )
  {
    CoTaskMemFree(v12);
    *(_QWORD *)(a1 + 56) = 0;
  }
  v13 = *(void **)(a1 + 104);
  if ( v13 )
  {
    CoTaskMemFree(v13);
    *(_QWORD *)(a1 + 104) = 0;
  }
  v14 = *(void **)(a1 + 96);
  if ( v14 )
  {
    CoTaskMemFree(v14);
    *(_QWORD *)(a1 + 96) = 0;
  }
  v15 = *(void **)(a1 + 120);
  if ( v15 )
  {
    CoTaskMemFree(v15);
    *(_QWORD *)(a1 + 120) = 0;
  }
  v16 = *(void **)(a1 + 112);
  if ( v16 )
  {
    CoTaskMemFree(v16);
    *(_QWORD *)(a1 + 112) = 0;
  }
  v17 = *(void **)(a1 + 160);
  if ( v17 )
  {
    CoTaskMemFree(v17);
    *(_QWORD *)(a1 + 160) = 0;
  }
  v18 = *(void **)(a1 + 168);
  if ( v18 )
  {
    CoTaskMemFree(v18);
    *(_QWORD *)(a1 + 168) = 0;
  }
}

```

## disassembly

```asm
0x140057a4c  push    rbx
0x140057a4e  push    rbp
0x140057a4f  push    rsi
0x140057a50  push    rdi
0x140057a51  push    r14
0x140057a53  sub     rsp, 20h
0x140057a57  xor     r14d, r14d
0x140057a5a  lea     rdi, [rcx+40h]
0x140057a5e  mov     rbx, rcx
0x140057a61  cmp     [rcx+48h], r14
0x140057a65  jz      short loc_140057AA0
0x140057a67  mov     esi, r14d
0x140057a6a  cmp     [rdi], r14d
0x140057a6d  jbe     short loc_140057A92
0x140057a6f  mov     rax, [rbx+48h]
0x140057a73  mov     ebp, esi
0x140057a75  mov     rcx, [rax+rbp*8]; pv
0x140057a79  test    rcx, rcx
0x140057a7c  jz      short loc_140057A8C
0x140057a7e  call    cs:__imp_CoTaskMemFree
0x140057a84  mov     rax, [rbx+48h]
0x140057a88  mov     [rax+rbp*8], r14
0x140057a8c  inc     esi
0x140057a8e  cmp     esi, [rdi]
0x140057a90  jb      short loc_140057A6F
0x140057a92  mov     rcx, [rbx+48h]; pv
0x140057a96  call    cs:__imp_CoTaskMemFree
0x140057a9c  mov     [rbx+48h], r14
0x140057aa0  cmp     [rbx+50h], r14
0x140057aa4  jz      short loc_140057ADF
0x140057aa6  mov     esi, r14d
0x140057aa9  cmp     [rdi], r14d
0x140057aac  jbe     short loc_140057AD1
0x140057aae  mov     rax, [rbx+50h]
0x140057ab2  mov     ebp, esi
0x140057ab4  mov     rcx, [rax+rbp*8]; pv
0x140057ab8  test    rcx, rcx
0x140057abb  jz      short loc_140057ACB
0x140057abd  call    cs:__imp_CoTaskMemFree
0x140057ac3  mov     rax, [rbx+50h]
0x140057ac7  mov     [rax+rbp*8], r14
0x140057acb  inc     esi
0x140057acd  cmp     esi, [rdi]
0x140057acf  jb      short loc_140057AAE
0x140057ad1  mov     rcx, [rbx+50h]; pv
0x140057ad5  call    cs:__imp_CoTaskMemFree
0x140057adb  mov     [rbx+50h], r14
0x140057adf  mov     rcx, [rbx+58h]; pv
0x140057ae3  test    rcx, rcx
0x140057ae6  jz      short loc_140057AF2
0x140057ae8  call    cs:__imp_CoTaskMemFree
0x140057aee  mov     [rbx+58h], r14
0x140057af2  mov     rcx, [rbx+80h]; pv
0x140057af9  test    rcx, rcx
0x140057afc  jz      short loc_140057B0B
0x140057afe  call    cs:__imp_CoTaskMemFree
0x140057b04  mov     [rbx+80h], r14
0x140057b0b  mov     rcx, [rbx+88h]; pv
0x140057b12  test    rcx, rcx
0x140057b15  jz      short loc_140057B24
0x140057b17  call    cs:__imp_CoTaskMemFree
0x140057b1d  mov     [rbx+88h], r14
0x140057b24  mov     rcx, [rbx+90h]; pv
0x140057b2b  test    rcx, rcx
0x140057b2e  jz      short loc_140057B3D
0x140057b30  call    cs:__imp_CoTaskMemFree
0x140057b36  mov     [rbx+90h], r14
0x140057b3d  mov     rcx, [rbx+98h]; pv
0x140057b44  test    rcx, rcx
0x140057b47  jz      short loc_140057B56
0x140057b49  call    cs:__imp_CoTaskMemFree
0x140057b4f  mov     [rbx+98h], r14
0x140057b56  mov     rcx, [rbx+38h]; pv
0x140057b5a  test    rcx, rcx
0x140057b5d  jz      short loc_140057B69
0x140057b5f  call    cs:__imp_CoTaskMemFree
0x140057b65  mov     [rbx+38h], r14
0x140057b69  mov     rcx, [rbx+68h]; pv
0x140057b6d  test    rcx, rcx
0x140057b70  jz      short loc_140057B7C
0x140057b72  call    cs:__imp_CoTaskMemFree
0x140057b78  mov     [rbx+68h], r14
0x140057b7c  mov     rcx, [rbx+60h]; pv
0x140057b80  test    rcx, rcx
0x140057b83  jz      short loc_140057B8F
0x140057b85  call    cs:__imp_CoTaskMemFree
0x140057b8b  mov     [rbx+60h], r14
0x140057b8f  mov     rcx, [rbx+78h]; pv
0x140057b93  test    rcx, rcx
0x140057b96  jz      short loc_140057BA2
0x140057b98  call    cs:__imp_CoTaskMemFree
0x140057b9e  mov     [rbx+78h], r14
0x140057ba2  mov     rcx, [rbx+70h]; pv
0x140057ba6  test    rcx, rcx
0x140057ba9  jz      short loc_140057BB5
0x140057bab  call    cs:__imp_CoTaskMemFree
0x140057bb1  mov     [rbx+70h], r14
0x140057bb5  mov     rcx, [rbx+0A0h]; pv
0x140057bbc  test    rcx, rcx
0x140057bbf  jz      short loc_140057BCE
0x140057bc1  call    cs:__imp_CoTaskMemFree
0x140057bc7  mov     [rbx+0A0h], r14
0x140057bce  mov     rcx, [rbx+0A8h]; pv
0x140057bd5  test    rcx, rcx
0x140057bd8  jz      short loc_140057BE7
0x140057bda  call    cs:__imp_CoTaskMemFree
0x140057be0  mov     [rbx+0A8h], r14
0x140057be7  add     rsp, 20h
0x140057beb  pop     r14
0x140057bed  pop     rdi
0x140057bee  pop     rsi
0x140057bef  pop     rbp
0x140057bf0  pop     rbx
0x140057bf1  retn
```
