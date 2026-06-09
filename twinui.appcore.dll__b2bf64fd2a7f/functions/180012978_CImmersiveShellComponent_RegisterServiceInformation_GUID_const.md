# CImmersiveShellComponent::RegisterServiceInformation(_GUID const &)

- ea: `0x180012978`
- end: `0x180012b47`
- name: `?RegisterServiceInformation@CImmersiveShellComponent@@QEAAJAEBU_GUID@@@Z`
- size: `463`
- prototype: `__int64 __fastcall(CImmersiveShellComponent *__hidden this, const struct _GUID *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800128a8`
- `0x180026394`

## callees

- `0x180012978`
- `0x18002bc68`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180012a65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180012a65`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180012a86`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180012a86`

## pseudocode

```c
__int64 __fastcall CImmersiveShellComponent::RegisterServiceInformation(
        CImmersiveShellComponent *this,
        const struct _GUID *a2)
{
  __int128 v2; // xmm0
  int v3; // edx
  int i; // ebp
  unsigned __int64 v6; // r8
  __int64 v7; // rdi
  unsigned __int64 v8; // rdi
  __int64 v9; // rax
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // r8
  unsigned __int64 v12; // r14
  char *v13; // r15
  unsigned __int64 v14; // r12
  _OWORD *v15; // r8
  LPMALLOC ppMalloc; // [rsp+78h] [rbp+10h] BYREF

  v2 = (__int128)*a2;
  v3 = 0;
  for ( i = 0; !i; i = 1 )
  {
    v6 = *((_QWORD *)this + 6);
    v3 = 0;
    v7 = *((_QWORD *)this + 4);
    if ( v7 != v6 )
      goto LABEL_23;
    v8 = v7 + 1;
    v3 = -2147024774;
    if ( v8 > 0xFFFFFFFE || (v3 = 0, v8 <= v6) )
    {
      if ( v3 >= 0 )
        goto LABEL_23;
    }
    else
    {
      ppMalloc = 0;
      v9 = 2 * v6;
      if ( is_mul_ok(v6, 2u) )
      {
        v10 = v6;
        v11 = v6 + 4096;
        if ( v10 <= 0x1000 )
          v11 = v9;
        if ( v8 <= v11 )
        {
          v8 = v11;
          if ( v11 > 0xFFFFFFFE )
            v8 = 4294967294LL;
        }
        ppMalloc = 0;
        v12 = 32 * v8;
        if ( is_mul_ok(v8, 0x20u) )
        {
          v13 = (char *)CoTaskMemRealloc(*((LPVOID *)this + 3), 32 * v8);
          if ( v13 )
          {
            ppMalloc = 0;
            if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
            {
              v14 = ((__int64 (__fastcall *)(LPMALLOC, char *))ppMalloc->lpVtbl->GetSize)(ppMalloc, v13);
              ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
              if ( v14 > v12 )
                memset_0(&v13[v12], 0, v14 - v12);
            }
            v3 = 0;
          }
          else
          {
            v3 = -2147024882;
          }
          if ( v3 < 0 )
            goto LABEL_25;
          *((_QWORD *)this + 6) = v8;
          *((_QWORD *)this + 3) = v13;
LABEL_23:
          ++*((_QWORD *)this + 4);
          v15 = (_OWORD *)(32LL * *((_QWORD *)this + 4) + *((_QWORD *)this + 3) - 32LL);
          if ( v15 )
          {
            *v15 = v2;
            v15[1] = 0;
          }
          goto LABEL_25;
        }
      }
      v3 = -2147024362;
    }
LABEL_25:
    if ( v3 < 0 )
      return (unsigned int)v3;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180012978  mov     rax, rsp
0x18001297b  mov     [rax+8], rbx
0x18001297f  mov     [rax+18h], rbp
0x180012983  push    rsi
0x180012984  push    rdi
0x180012985  push    r12
0x180012987  push    r14
0x180012989  push    r15
0x18001298b  sub     rsp, 40h
0x18001298f  movups  xmm0, xmmword ptr [rdx]
0x180012992  xor     edx, edx
0x180012994  mov     rbx, rcx
0x180012997  xorps   xmm1, xmm1
0x18001299a  xor     ebp, ebp
0x18001299c  movdqu  xmmword ptr [rax-48h], xmm0
0x1800129a1  mov     r9d, 0FFFFFFFEh
0x1800129a7  movdqu  xmmword ptr [rax-38h], xmm1
0x1800129ac  cmp     ebp, 1
0x1800129af  jnb     loc_180012B2C
0x1800129b5  mov     esi, ebp
0x1800129b7  shl     rsi, 5
0x1800129bb  mov     rcx, qword ptr [rsp+rsi+68h+var_38]
0x1800129c0  test    rcx, rcx
0x1800129c3  jz      short loc_1800129D7
0x1800129c5  mov     rax, [rcx]
0x1800129c8  mov     rax, [rax+8]
0x1800129cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129d1  mov     r9d, 0FFFFFFFEh
0x1800129d7  mov     r8, [rbx+30h]
0x1800129db  xor     edx, edx
0x1800129dd  mov     rdi, [rbx+20h]
0x1800129e1  cmp     rdi, r8
0x1800129e4  jnz     loc_180012AF0
0x1800129ea  inc     rdi
0x1800129ed  mov     edx, 8007007Ah
0x1800129f2  cmp     rdi, r9
0x1800129f5  ja      loc_180012AEC
0x1800129fb  xor     edx, edx
0x1800129fd  cmp     rdi, r8
0x180012a00  jbe     loc_180012AEC
0x180012a06  lea     eax, [rdx+2]
0x180012a09  mov     [rsp+68h+ppMalloc], rdx
0x180012a0e  mul     r8
0x180012a11  test    rdx, rdx
0x180012a14  jnz     loc_180012AE5
0x180012a1a  mov     rcx, rax
0x180012a1d  sub     rcx, r8
0x180012a20  add     r8, 1000h
0x180012a27  cmp     rcx, 1000h
0x180012a2e  cmovbe  r8, rax
0x180012a32  cmp     rdi, r8
0x180012a35  ja      short loc_180012A41
0x180012a37  cmp     r8, r9
0x180012a3a  mov     rdi, r8
0x180012a3d  cmova   rdi, r9
0x180012a41  mov     eax, 20h ; ' '
0x180012a46  mov     [rsp+68h+ppMalloc], 0
0x180012a4f  mul     rdi
0x180012a52  mov     r14, rax
0x180012a55  test    rdx, rdx
0x180012a58  jnz     loc_180012AE5
0x180012a5e  mov     rcx, [rbx+18h]; pv
0x180012a62  mov     rdx, rax; cb
0x180012a65  call    cs:__imp_CoTaskMemRealloc
0x180012a6b  mov     r15, rax
0x180012a6e  test    rax, rax
0x180012a71  jz      short loc_180012AD2
0x180012a73  lea     rdx, [rsp+68h+ppMalloc]; ppMalloc
0x180012a78  mov     [rsp+68h+ppMalloc], 0
0x180012a81  mov     ecx, 1; dwMemContext
0x180012a86  call    cs:__imp_CoGetMalloc
0x180012a8c  test    eax, eax
0x180012a8e  js      short loc_180012ACE
0x180012a90  mov     rcx, [rsp+68h+ppMalloc]
0x180012a95  mov     rdx, r15
0x180012a98  mov     rax, [rcx]
0x180012a9b  mov     rax, [rax+30h]
0x180012a9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012aa4  mov     rcx, [rsp+68h+ppMalloc]
0x180012aa9  mov     r12, rax
0x180012aac  mov     rax, [rcx]
0x180012aaf  mov     rax, [rax+10h]
0x180012ab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ab8  cmp     r12, r14
0x180012abb  jbe     short loc_180012ACE
0x180012abd  sub     r12, r14
0x180012ac0  lea     rcx, [r14+r15]; void *
0x180012ac4  mov     r8, r12; Size
0x180012ac7  xor     edx, edx; Val
0x180012ac9  call    memset_0
0x180012ace  xor     edx, edx
0x180012ad0  jmp     short loc_180012AD7
0x180012ad2  mov     edx, 8007000Eh
0x180012ad7  test    edx, edx
0x180012ad9  js      short loc_180012B1C
0x180012adb  mov     [rbx+30h], rdi
0x180012adf  mov     [rbx+18h], r15
0x180012ae3  jmp     short loc_180012AF0
0x180012ae5  mov     edx, 80070216h
0x180012aea  jmp     short loc_180012B1C
0x180012aec  test    edx, edx
0x180012aee  js      short loc_180012B1C
0x180012af0  inc     qword ptr [rbx+20h]
0x180012af4  mov     rcx, [rbx+20h]
0x180012af8  mov     r8, [rbx+18h]
0x180012afc  shl     rcx, 5
0x180012b00  add     r8, 0FFFFFFFFFFFFFFE0h
0x180012b04  add     r8, rcx
0x180012b07  jz      short loc_180012B1C
0x180012b09  movups  xmm0, [rsp+rsi+68h+var_48]
0x180012b0e  movups  xmm1, [rsp+rsi+68h+var_38]
0x180012b13  movups  xmmword ptr [r8], xmm0
0x180012b17  movups  xmmword ptr [r8+10h], xmm1
0x180012b1c  inc     ebp
0x180012b1e  mov     r9d, 0FFFFFFFEh
0x180012b24  test    edx, edx
0x180012b26  jns     loc_1800129AC
0x180012b2c  lea     r11, [rsp+68h+var_28]
0x180012b31  mov     eax, edx
0x180012b33  mov     rbx, [r11+30h]
0x180012b37  mov     rbp, [r11+40h]
0x180012b3b  mov     rsp, r11
0x180012b3e  pop     r15
0x180012b40  pop     r14
0x180012b42  pop     r12
0x180012b44  pop     rdi
0x180012b45  pop     rsi
0x180012b46  retn
```
