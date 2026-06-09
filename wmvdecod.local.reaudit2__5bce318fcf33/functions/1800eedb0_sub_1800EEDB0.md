# sub_1800EEDB0

- ea: `0x1800eedb0`
- end: `0x1800ef052`
- name: `sub_1800EEDB0`
- size: `674`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x18009904c`
- `0x180099098`
- `0x1800994a0`
- `0x1800ad3e0`
- `0x1800eedb0`
- `0x1800ef090`
- `0x1800f7960`
- `0x18020c9b0`
- `0x18020ca70`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800eedfa`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800eedfa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ef019`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ef019`

## pseudocode

```c
__int64 __fastcall sub_1800EEDB0(__int64 a1, unsigned int a2, __int64 a3)
{
  int v4; // edi
  DWORD TickCount; // eax
  __int64 v8; // rcx
  unsigned int i; // esi
  __int64 v10; // rax
  __int64 result; // rax
  unsigned int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rdi
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rdi
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rcx
  _BYTE *v27; // rax
  unsigned int v28; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v30[4096]; // [rsp+40h] [rbp-C0h] BYREF
  char v31; // [rsp+1040h] [rbp+F40h]
  _BYTE v32[24]; // [rsp+1050h] [rbp+F50h] BYREF

  v4 = 0;
  pv = 0;
  TickCount = GetTickCount();
  v8 = 0;
  v31 = 0;
  do
  {
    TickCount = ((int)(214013 * TickCount + 2531011) >> 16) & 0x7FFF;
    v30[v8++] = TickCount;
  }
  while ( v8 != 4096 );
  for ( i = 0; i < *(_DWORD *)(a1 + 48); ++i )
  {
    if ( pv )
      break;
    v10 = *(_QWORD *)(a1 + 40);
    v28 = 0;
    result = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)(v10 + 8LL * i) + 24LL))(
               *(_QWORD *)(v10 + 8LL * i),
               &v28);
    v4 = result;
    if ( (int)result < 0 )
      return result;
    v12 = v28;
    if ( a2 < v28 )
    {
      v13 = *(_QWORD *)(*(_QWORD *)(a1 + 40) + 8LL * i);
      result = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *, LPVOID *))(*(_QWORD *)v13 + 40LL))(
                 v13,
                 a2,
                 a3,
                 qword_18021EAA0,
                 &pv);
      v4 = result;
      if ( (int)result < 0 )
        return result;
      v12 = v28;
    }
    a2 -= v12;
  }
  if ( !*(_QWORD *)(a1 + 80) )
  {
    v14 = sub_18009904C(16);
    *(_QWORD *)(a1 + 80) = v14;
    v15 = v14;
    if ( v14 )
    {
      memcpy(v30, qword_18021EB10, sizeof(v30));
      v31 = 1;
      if ( (int)sub_1800EF090(v30, v32) < 0 )
      {
        j__o_free(v15, v16);
        *(_QWORD *)(a1 + 80) = 0;
        v15 = 0;
      }
      v4 = sub_1800F7960(v17, v32, pv, v15);
      if ( v4 < 0 )
      {
        v19 = *(_QWORD *)(a1 + 80);
        if ( v19 )
        {
          j__o_free(v19, v18);
          *(_QWORD *)(a1 + 80) = 0;
        }
      }
      goto LABEL_25;
    }
    return 2147942414LL;
  }
  if ( !*(_QWORD *)(a1 + 88) )
  {
    v20 = sub_18009904C(16);
    *(_QWORD *)(a1 + 88) = v20;
    v21 = v20;
    if ( v20 )
    {
      memcpy(v30, qword_18021EB10, sizeof(v30));
      v31 = 1;
      if ( (int)sub_1800EF090(v30, v32) < 0 )
      {
        j__o_free(v21, v22);
        *(_QWORD *)(a1 + 88) = 0;
        v21 = 0;
      }
      v4 = sub_1800F7960(v23, v32, pv, v21);
      if ( v4 < 0 )
      {
        v25 = *(_QWORD *)(a1 + 88);
        if ( v25 )
        {
          j__o_free(v25, v24);
          *(_QWORD *)(a1 + 88) = 0;
        }
      }
      goto LABEL_25;
    }
    return 2147942414LL;
  }
LABEL_25:
  v26 = 20;
  v27 = v32;
  do
  {
    *v27++ = 0;
    --v26;
  }
  while ( v26 );
  if ( pv )
    CoTaskMemFree(pv);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800eedb0  mov     [rsp-8+arg_18], rbx
0x1800eedb5  push    rbp
0x1800eedb6  push    rsi
0x1800eedb7  push    rdi
0x1800eedb8  push    r12
0x1800eedba  push    r13
0x1800eedbc  push    r14
0x1800eedbe  push    r15
0x1800eedc0  lea     rbp, [rsp-0F70h]
0x1800eedc8  mov     eax, 1070h
0x1800eedcd  call    __alloca_probe
0x1800eedd2  sub     rsp, rax
0x1800eedd5  mov     rax, cs:__security_cookie
0x1800eeddc  xor     rax, rsp
0x1800eeddf  mov     [rbp+0FA0h+var_38], rax
0x1800eede6  xor     r13d, r13d
0x1800eede9  mov     r12, r8
0x1800eedec  mov     edi, r13d
0x1800eedef  mov     [rsp+10A0h+pv], r13
0x1800eedf4  mov     r14d, edx
0x1800eedf7  mov     rbx, rcx
0x1800eedfa  call    cs:GetTickCount
0x1800eee01  nop     dword ptr [rax+rax+00h]
0x1800eee06  mov     ecx, r13d
0x1800eee09  mov     [rbp+0FA0h+var_60], r13b
0x1800eee10  imul    eax, 343FDh
0x1800eee16  add     eax, 269EC3h
0x1800eee1b  sar     eax, 10h
0x1800eee1e  and     eax, 7FFFh
0x1800eee23  mov     [rsp+rcx+10A0h+var_1060], al
0x1800eee27  inc     rcx
0x1800eee2a  cmp     rcx, 1000h
0x1800eee31  jnz     short loc_1800EEE10
0x1800eee33  mov     esi, r13d
0x1800eee36  cmp     [rbx+30h], r13d
0x1800eee3a  jbe     loc_1800EEEC0
0x1800eee40  cmp     [rsp+10A0h+pv], r13
0x1800eee45  jnz     short loc_1800EEEC0
0x1800eee47  mov     rax, [rbx+28h]
0x1800eee4b  lea     rdx, [rsp+10A0h+var_1070]
0x1800eee50  mov     [rsp+10A0h+var_1070], r13d
0x1800eee55  mov     r15d, esi
0x1800eee58  mov     rcx, [rax+r15*8]
0x1800eee5c  mov     rax, [rcx]
0x1800eee5f  mov     rax, [rax+18h]
0x1800eee63  call    cs:__guard_dispatch_icall_fptr
0x1800eee69  mov     edi, eax
0x1800eee6b  test    eax, eax
0x1800eee6d  js      loc_1800EF027
0x1800eee73  mov     eax, [rsp+10A0h+var_1070]
0x1800eee77  cmp     r14d, eax
0x1800eee7a  jnb     short loc_1800EEEB6
0x1800eee7c  mov     rax, [rbx+28h]
0x1800eee80  lea     rdx, [rsp+10A0h+pv]
0x1800eee85  mov     [rsp+10A0h+var_1080], rdx
0x1800eee8a  lea     r9, qword_18021EAA0
0x1800eee91  mov     r8, r12
0x1800eee94  mov     edx, r14d
0x1800eee97  mov     rcx, [rax+r15*8]
0x1800eee9b  mov     rax, [rcx]
0x1800eee9e  mov     rax, [rax+28h]
0x1800eeea2  call    cs:__guard_dispatch_icall_fptr
0x1800eeea8  mov     edi, eax
0x1800eeeaa  test    eax, eax
0x1800eeeac  js      loc_1800EF027
0x1800eeeb2  mov     eax, [rsp+10A0h+var_1070]
0x1800eeeb6  sub     r14d, eax
0x1800eeeb9  inc     esi
0x1800eeebb  cmp     esi, [rbx+30h]
0x1800eeebe  jb      short loc_1800EEE40
0x1800eeec0  cmp     [rbx+50h], r13
0x1800eeec4  jnz     loc_1800EEF5F
0x1800eeeca  mov     ecx, 10h
0x1800eeecf  call    sub_18009904C
0x1800eeed4  mov     [rbx+50h], rax
0x1800eeed8  mov     rdi, rax
0x1800eeedb  test    rax, rax
0x1800eeede  jz      loc_1800EEF7F
0x1800eeee4  mov     r8d, 1000h; Size
0x1800eeeea  lea     rdx, qword_18021EB10; Src
0x1800eeef1  lea     rcx, [rsp+10A0h+var_1060]; void *
0x1800eeef6  call    memcpy
0x1800eeefb  lea     rdx, [rbp+0FA0h+var_50]
0x1800eef02  mov     [rbp+0FA0h+var_60], 1
0x1800eef09  lea     rcx, [rsp+10A0h+var_1060]
0x1800eef0e  call    sub_1800EF090
0x1800eef13  test    eax, eax
0x1800eef15  jns     short loc_1800EEF26
0x1800eef17  mov     rcx, rdi
0x1800eef1a  call    j__o_free
0x1800eef1f  mov     [rbx+50h], r13
0x1800eef23  mov     rdi, r13
0x1800eef26  mov     r8, [rsp+10A0h+pv]
0x1800eef2b  lea     rdx, [rbp+0FA0h+var_50]
0x1800eef32  mov     r9, rdi
0x1800eef35  call    sub_1800F7960
0x1800eef3a  mov     edi, eax
0x1800eef3c  test    eax, eax
0x1800eef3e  jns     loc_1800EEFF7
0x1800eef44  mov     rcx, [rbx+50h]
0x1800eef48  test    rcx, rcx
0x1800eef4b  jz      loc_1800EEFF7
0x1800eef51  call    j__o_free
0x1800eef56  mov     [rbx+50h], r13
0x1800eef5a  jmp     loc_1800EEFF7
0x1800eef5f  cmp     [rbx+58h], r13
0x1800eef63  jnz     loc_1800EEFF7
0x1800eef69  mov     ecx, 10h
0x1800eef6e  call    sub_18009904C
0x1800eef73  mov     [rbx+58h], rax
0x1800eef77  mov     rdi, rax
0x1800eef7a  test    rax, rax
0x1800eef7d  jnz     short loc_1800EEF89
0x1800eef7f  mov     eax, 8007000Eh
0x1800eef84  jmp     loc_1800EF027
0x1800eef89  mov     r8d, 1000h; Size
0x1800eef8f  lea     rdx, qword_18021EB10; Src
0x1800eef96  lea     rcx, [rsp+10A0h+var_1060]; void *
0x1800eef9b  call    memcpy
0x1800eefa0  lea     rdx, [rbp+0FA0h+var_50]
0x1800eefa7  mov     [rbp+0FA0h+var_60], 1
0x1800eefae  lea     rcx, [rsp+10A0h+var_1060]
0x1800eefb3  call    sub_1800EF090
0x1800eefb8  test    eax, eax
0x1800eefba  jns     short loc_1800EEFCB
0x1800eefbc  mov     rcx, rdi
0x1800eefbf  call    j__o_free
0x1800eefc4  mov     [rbx+58h], r13
0x1800eefc8  mov     rdi, r13
0x1800eefcb  mov     r8, [rsp+10A0h+pv]
0x1800eefd0  lea     rdx, [rbp+0FA0h+var_50]
0x1800eefd7  mov     r9, rdi
0x1800eefda  call    sub_1800F7960
0x1800eefdf  mov     edi, eax
0x1800eefe1  test    eax, eax
0x1800eefe3  jns     short loc_1800EEFF7
0x1800eefe5  mov     rcx, [rbx+58h]
0x1800eefe9  test    rcx, rcx
0x1800eefec  jz      short loc_1800EEFF7
0x1800eefee  call    j__o_free
0x1800eeff3  mov     [rbx+58h], r13
0x1800eeff7  mov     ecx, 14h
0x1800eeffc  lea     rax, [rbp+0FA0h+var_50]
0x1800ef003  mov     [rax], r13b
0x1800ef006  inc     rax
0x1800ef009  sub     rcx, 1
0x1800ef00d  jnz     short loc_1800EF003
0x1800ef00f  mov     rcx, [rsp+10A0h+pv]; pv
0x1800ef014  test    rcx, rcx
0x1800ef017  jz      short loc_1800EF025
0x1800ef019  call    cs:CoTaskMemFree
0x1800ef020  nop     dword ptr [rax+rax+00h]
0x1800ef025  mov     eax, edi
0x1800ef027  mov     rcx, [rbp+0FA0h+var_38]
0x1800ef02e  xor     rcx, rsp; StackCookie
0x1800ef031  call    __security_check_cookie
0x1800ef036  mov     rbx, [rsp+10A0h+arg_18]
0x1800ef03e  add     rsp, 1070h
0x1800ef045  pop     r15
0x1800ef047  pop     r14
0x1800ef049  pop     r13
0x1800ef04b  pop     r12
0x1800ef04d  pop     rdi
0x1800ef04e  pop     rsi
0x1800ef04f  pop     rbp
0x1800ef050  retn
```
