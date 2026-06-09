# DsqFreeObject(tagDSDeployment *,ulong)

- ea: `0x1801335f4`
- end: `0x18013370c`
- name: `?DsqFreeObject@@YAXPEAUtagDSDeployment@@K@Z`
- size: `280`
- prototype: `void __fastcall(struct tagDSDeployment *, unsigned int)`
- caller_count: `13`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003cac8`
- `0x180045d30`
- `0x180052894`
- `0x180052be0`
- `0x18005fd1c`
- `0x1800666b4`
- `0x180067714`
- `0x180087174`
- `0x180093614`
- `0x1800a7620`
- `0x1800a9ecc`
- `0x1800b51d8`
- `0x180195720`

## callees

- `0x1801335f4`
- `0x180240d40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180133641`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180133656`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180133665`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180133674`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180133683`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180133692`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801336a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801336b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801336bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801336ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180133641`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180133656`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180133665`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180133674`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180133683`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180133692`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801336a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801336b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801336bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801336ce`

## pseudocode

```c
void __fastcall DsqFreeObject(struct tagDSDeployment *a1, unsigned int a2)
{
  struct tagDSDeployment *v2; // rdi
  char *v3; // rbx
  __int64 v4; // rbp
  __int64 i; // rsi
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx

  if ( a1 )
  {
    v2 = a1;
    if ( a2 )
    {
      v3 = (char *)a1 + 40;
      v4 = a2;
      do
      {
        for ( i = 0; (unsigned int)i < *((_DWORD *)v3 - 1); i = (unsigned int)(i + 1) )
        {
          v6 = *(void **)(*(_QWORD *)v3 + 8 * i);
          if ( v6 )
            CoTaskMemFree(v6);
        }
        if ( *(_QWORD *)v3 )
          CoTaskMemFree(*(LPVOID *)v3);
        v7 = (void *)*((_QWORD *)v3 + 7);
        if ( v7 )
          CoTaskMemFree(v7);
        v8 = (void *)*((_QWORD *)v3 + 8);
        if ( v8 )
          CoTaskMemFree(v8);
        v9 = (void *)*((_QWORD *)v3 + 10);
        if ( v9 )
          CoTaskMemFree(v9);
        v10 = (void *)*((_QWORD *)v3 + 11);
        if ( v10 )
          CoTaskMemFree(v10);
        v11 = (void *)*((_QWORD *)v3 + 12);
        if ( v11 )
          CoTaskMemFree(v11);
        v12 = (void *)*((_QWORD *)v3 + 13);
        if ( v12 )
          CoTaskMemFree(v12);
        v13 = (void *)*((_QWORD *)v3 + 14);
        if ( v13 )
          CoTaskMemFree(v13);
        v14 = (void *)*((_QWORD *)v3 + 15);
        if ( v14 )
          CoTaskMemFree(v14);
        memset(v2, 0, 0xA8u);
        v2 = (struct tagDSDeployment *)((char *)v2 + 168);
        v3 += 168;
        --v4;
      }
      while ( v4 );
    }
  }
}

```

## disassembly

```asm
0x1801335f4  test    rcx, rcx
0x1801335f7  jz      locret_18013370B
0x1801335fd  mov     rax, rsp
0x180133600  mov     [rax+8], rbx
0x180133604  mov     [rax+10h], rbp
0x180133608  mov     [rax+18h], rsi
0x18013360c  mov     [rax+20h], rdi
0x180133610  push    r14
0x180133612  sub     rsp, 20h
0x180133616  mov     rdi, rcx
0x180133619  cmp     edx, 1
0x18013361c  jb      loc_1801336F1
0x180133622  lea     rbx, [rcx+28h]
0x180133626  mov     ebp, edx
0x180133628  mov     r14d, 0A8h
0x18013362e  xor     esi, esi
0x180133630  cmp     [rbx-4], esi
0x180133633  jbe     short loc_18013364E
0x180133635  mov     rax, [rbx]
0x180133638  mov     rcx, [rax+rsi*8]; pv
0x18013363c  test    rcx, rcx
0x18013363f  jz      short loc_180133647
0x180133641  call    cs:__imp_CoTaskMemFree
0x180133647  inc     esi
0x180133649  cmp     esi, [rbx-4]
0x18013364c  jb      short loc_180133635
0x18013364e  mov     rcx, [rbx]; pv
0x180133651  test    rcx, rcx
0x180133654  jz      short loc_18013365C
0x180133656  call    cs:__imp_CoTaskMemFree
0x18013365c  mov     rcx, [rbx+38h]; pv
0x180133660  test    rcx, rcx
0x180133663  jz      short loc_18013366B
0x180133665  call    cs:__imp_CoTaskMemFree
0x18013366b  mov     rcx, [rbx+40h]; pv
0x18013366f  test    rcx, rcx
0x180133672  jz      short loc_18013367A
0x180133674  call    cs:__imp_CoTaskMemFree
0x18013367a  mov     rcx, [rbx+50h]; pv
0x18013367e  test    rcx, rcx
0x180133681  jz      short loc_180133689
0x180133683  call    cs:__imp_CoTaskMemFree
0x180133689  mov     rcx, [rbx+58h]; pv
0x18013368d  test    rcx, rcx
0x180133690  jz      short loc_180133698
0x180133692  call    cs:__imp_CoTaskMemFree
0x180133698  mov     rcx, [rbx+60h]; pv
0x18013369c  test    rcx, rcx
0x18013369f  jz      short loc_1801336A7
0x1801336a1  call    cs:__imp_CoTaskMemFree
0x1801336a7  mov     rcx, [rbx+68h]; pv
0x1801336ab  test    rcx, rcx
0x1801336ae  jz      short loc_1801336B6
0x1801336b0  call    cs:__imp_CoTaskMemFree
0x1801336b6  mov     rcx, [rbx+70h]; pv
0x1801336ba  test    rcx, rcx
0x1801336bd  jz      short loc_1801336C5
0x1801336bf  call    cs:__imp_CoTaskMemFree
0x1801336c5  mov     rcx, [rbx+78h]; pv
0x1801336c9  test    rcx, rcx
0x1801336cc  jz      short loc_1801336D4
0x1801336ce  call    cs:__imp_CoTaskMemFree
0x1801336d4  mov     r8, r14; Size
0x1801336d7  xor     edx, edx; Val
0x1801336d9  mov     rcx, rdi; void *
0x1801336dc  call    memset
0x1801336e1  add     rdi, r14
0x1801336e4  add     rbx, r14
0x1801336e7  sub     rbp, 1
0x1801336eb  jnz     loc_18013362E
0x1801336f1  mov     rbx, [rsp+28h+arg_0]
0x1801336f6  mov     rbp, [rsp+28h+arg_8]
0x1801336fb  mov     rsi, [rsp+28h+arg_10]
0x180133700  mov     rdi, [rsp+28h+arg_18]
0x180133705  add     rsp, 20h
0x180133709  pop     r14
0x18013370b  retn
```
