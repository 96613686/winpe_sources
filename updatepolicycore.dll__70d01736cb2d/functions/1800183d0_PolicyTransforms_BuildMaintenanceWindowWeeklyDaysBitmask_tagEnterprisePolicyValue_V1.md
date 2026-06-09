# PolicyTransforms::BuildMaintenanceWindowWeeklyDaysBitmask(tagEnterprisePolicyValue_V1 *)

- ea: `0x1800183d0`
- end: `0x180018581`
- name: `?BuildMaintenanceWindowWeeklyDaysBitmask@PolicyTransforms@@SAJPEAUtagEnterprisePolicyValue_V1@@@Z`
- size: `433`
- prototype: `__int64 __fastcall(struct tagEnterprisePolicyValue_V1 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config, service_task`

## callees

- `0x18000aac0`
- `0x180010ae0`
- `0x1800183d0`
- `0x18002ffd0`
- `0x18003002c`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1800184de`
- `OLEAUT32!__imp_VariantClear` at `0x180018522`
- `OLEAUT32!__imp_VariantClear` at `0x18001856b`
- `OLEAUT32!__imp_VariantClear` at `0x1800184de`
- `OLEAUT32!__imp_VariantClear` at `0x180018522`
- `OLEAUT32!__imp_VariantClear` at `0x18001856b`

## pseudocode

```c
__int64 __fastcall PolicyTransforms::BuildMaintenanceWindowWeeklyDaysBitmask(struct tagEnterprisePolicyValue_V1 *a1)
{
  HRESULT v2; // ebx
  __int64 v3; // rdx
  int v5; // esi
  int v6; // r15d
  char v7; // r14
  unsigned int *v8; // rdi
  int PolicyWithFallback; // eax
  void *v10; // rcx
  _WORD *v11; // rdi
  int v12[14]; // [rsp+20h] [rbp-60h] BYREF
  void **p_Block; // [rsp+58h] [rbp-28h] BYREF
  char v14; // [rsp+60h] [rbp-20h]
  void *Block; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  if ( !a1 )
  {
    v2 = -2147467261;
    v3 = 1622;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\Enterprise\\PolicyTransforms.cpp",
      (const char *)(unsigned int)v2,
      v12[0]);
    return (unsigned int)v2;
  }
  v12[0] = 75;
  v12[1] = 1;
  v12[2] = 76;
  v12[3] = 2;
  v12[4] = 77;
  v12[5] = 4;
  v12[6] = 78;
  v12[7] = 8;
  v12[8] = 79;
  v12[9] = 16;
  v12[10] = 80;
  v12[11] = 32;
  v12[12] = 81;
  v12[13] = 64;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  v8 = (unsigned int *)v12;
  do
  {
    Block = 0;
    p_Block = &Block;
    v14 = 1;
    PolicyWithFallback = EnterprisePolicyReader::ReadPolicyWithFallback(*v8, (__int64 *)&Block);
    v10 = Block;
    if ( PolicyWithFallback >= 0 && *((_DWORD *)Block + 1) == 1 && *((_DWORD *)Block + 6) == 1 )
    {
      v5 |= v8[1];
      v6 = *((_DWORD *)Block + 2);
      v7 = 1;
    }
    v14 = 0;
    if ( Block )
    {
      VariantClear((VARIANTARG *)((char *)Block + 16));
      v10 = Block;
    }
    if ( v10 )
      operator delete(v10);
    v8 += 2;
  }
  while ( v8 != (unsigned int *)&p_Block );
  v11 = (_WORD *)((char *)a1 + 16);
  if ( v7 )
  {
    if ( *v11 )
    {
      if ( *v11 != 3 )
        VariantClear((VARIANTARG *)((char *)a1 + 16));
    }
    *v11 = 3;
    *((_DWORD *)a1 + 6) = v5;
    *((_DWORD *)a1 + 1) = 1;
    *((_DWORD *)a1 + 2) = v6;
  }
  else
  {
    *(_QWORD *)((char *)a1 + 4) = 0;
    v2 = VariantClear((VARIANTARG *)((char *)a1 + 16));
    if ( v2 < 0 )
    {
      v3 = 1679;
      goto LABEL_3;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800183d0  mov     [rsp-28h+arg_8], rbx
0x1800183d5  mov     [rsp-28h+arg_10], rsi
0x1800183da  push    rbp
0x1800183db  push    rdi
0x1800183dc  push    r12
0x1800183de  push    r14
0x1800183e0  push    r15
0x1800183e2  mov     rbp, rsp
0x1800183e5  sub     rsp, 80h
0x1800183ec  mov     rax, cs:__security_cookie
0x1800183f3  xor     rax, rsp
0x1800183f6  mov     [rbp+var_10], rax
0x1800183fa  mov     rbx, rcx
0x1800183fd  xor     r12d, r12d
0x180018400  test    rcx, rcx
0x180018403  jnz     short loc_180018429
0x180018405  mov     ebx, 80004003h
0x18001840a  mov     edx, 656h; void *
0x18001840f  lea     r8, aCW1SSrcClientP_0; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x180018416  mov     r9d, ebx; char *
0x180018419  mov     rcx, [rbp+28h]; this
0x18001841d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018422  mov     eax, ebx
0x180018424  jmp     loc_18001853C
0x180018429  mov     [rbp+var_60], 4Bh ; 'K'
0x180018430  mov     [rbp+var_5C], 1
0x180018437  mov     [rbp+var_58], 4Ch ; 'L'
0x18001843e  mov     [rbp+var_54], 2
0x180018445  mov     [rbp+var_50], 4Dh ; 'M'
0x18001844c  mov     [rbp+var_4C], 4
0x180018453  mov     [rbp+var_48], 4Eh ; 'N'
0x18001845a  mov     [rbp+var_44], 8
0x180018461  mov     [rbp+var_40], 4Fh ; 'O'
0x180018468  mov     [rbp+var_3C], 10h
0x18001846f  mov     [rbp+var_38], 50h ; 'P'
0x180018476  mov     [rbp+var_34], 20h ; ' '
0x18001847d  mov     [rbp+var_30], 51h ; 'Q'
0x180018484  mov     [rbp+var_2C], 40h ; '@'
0x18001848b  mov     esi, r12d
0x18001848e  mov     r15d, r12d
0x180018491  mov     r14b, r12b
0x180018494  lea     rdi, [rbp+var_60]
0x180018498  mov     [rbp+Block], r12
0x18001849c  lea     rax, [rbp+Block]
0x1800184a0  mov     [rbp+var_28], rax
0x1800184a4  mov     [rbp+var_20], 1
0x1800184a8  lea     rdx, [rbp+Block]
0x1800184ac  mov     ecx, [rdi]
0x1800184ae  call    ?ReadPolicyWithFallback@EnterprisePolicyReader@@SAJW4tagEnterprisePolicy@@PEAPEAUtagEnterprisePolicyValue_V1@@@Z; EnterprisePolicyReader::ReadPolicyWithFallback(tagEnterprisePolicy,tagEnterprisePolicyValue_V1 * *)
0x1800184b3  mov     rcx, [rbp+Block]
0x1800184b7  test    eax, eax
0x1800184b9  js      short loc_1800184D1
0x1800184bb  cmp     dword ptr [rcx+4], 1
0x1800184bf  jnz     short loc_1800184D1
0x1800184c1  cmp     dword ptr [rcx+18h], 1
0x1800184c5  jnz     short loc_1800184D1
0x1800184c7  or      esi, [rdi+4]
0x1800184ca  mov     r15d, [rcx+8]
0x1800184ce  mov     r14b, 1
0x1800184d1  mov     [rbp+var_20], r12b
0x1800184d5  test    rcx, rcx
0x1800184d8  jz      short loc_1800184E8
0x1800184da  add     rcx, 10h; pvarg
0x1800184de  call    cs:__imp_VariantClear
0x1800184e4  mov     rcx, [rbp+Block]; Block
0x1800184e8  test    rcx, rcx
0x1800184eb  jz      short loc_1800184F7
0x1800184ed  mov     edx, 30h ; '0'
0x1800184f2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800184f7  add     rdi, 8
0x1800184fb  lea     rax, [rbp+var_28]
0x1800184ff  cmp     rdi, rax
0x180018502  jnz     short loc_180018498
0x180018504  lea     rdi, [rbx+10h]
0x180018508  test    r14b, r14b
0x18001850b  jz      short loc_180018564
0x18001850d  mov     r14d, 3
0x180018513  cmp     [rdi], r12w
0x180018517  jz      short loc_180018528
0x180018519  cmp     [rdi], r14w
0x18001851d  jz      short loc_180018528
0x18001851f  mov     rcx, rdi; pvarg
0x180018522  call    cs:__imp_VariantClear
0x180018528  mov     [rdi], r14w
0x18001852c  mov     [rbx+18h], esi
0x18001852f  mov     dword ptr [rbx+4], 1
0x180018536  mov     [rbx+8], r15d
0x18001853a  xor     eax, eax
0x18001853c  mov     rcx, [rbp+var_10]
0x180018540  xor     rcx, rsp; StackCookie
0x180018543  call    __security_check_cookie
0x180018548  lea     r11, [rsp+80h+var_s0]
0x180018550  mov     rbx, [r11+38h]
0x180018554  mov     rsi, [r11+40h]
0x180018558  mov     rsp, r11
0x18001855b  pop     r15
0x18001855d  pop     r14
0x18001855f  pop     r12
0x180018561  pop     rdi
0x180018562  pop     rbp
0x180018563  retn
0x180018564  mov     [rbx+4], r12
0x180018568  mov     rcx, rdi; pvarg
0x18001856b  call    cs:__imp_VariantClear
0x180018571  mov     ebx, eax
0x180018573  test    eax, eax
0x180018575  jns     short loc_18001853A
0x180018577  mov     edx, 68Fh
0x18001857c  jmp     loc_18001840F
```
