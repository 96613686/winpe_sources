# CUtils::FreeSessionInformation(ulong,_TS_SESSION_INFORMATION_0 *)

- ea: `0x1800a1458`
- end: `0x1800a14bf`
- name: `?FreeSessionInformation@CUtils@@SAXKPEAU_TS_SESSION_INFORMATION_0@@@Z`
- size: `103`
- prototype: `static void(unsigned int, struct _TS_SESSION_INFORMATION_0 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180077a74`
- `0x18007b4b4`

## callees

- `0x1800a1458`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a147e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a1494`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a14a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a147e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a1494`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a14a9`

## pseudocode

```c
void __fastcall CUtils::FreeSessionInformation(unsigned int a1, struct _TS_SESSION_INFORMATION_0 *a2)
{
  __int64 i; // rdi
  void *v5; // rcx
  void *v6; // rcx

  if ( a2 )
  {
    for ( i = 0; (unsigned int)i < a1; i = (unsigned int)(i + 1) )
    {
      v5 = (void *)*((_QWORD *)a2 + 3 * i + 2);
      if ( v5 )
        CoTaskMemFree(v5);
      v6 = (void *)*((_QWORD *)a2 + 3 * i + 1);
      if ( v6 )
        CoTaskMemFree(v6);
    }
    CoTaskMemFree(a2);
  }
}

```

## disassembly

```asm
0x1800a1458  test    rdx, rdx
0x1800a145b  jz      short locret_1800A14BD
0x1800a145d  push    rbx
0x1800a145e  push    rbp
0x1800a145f  push    rsi
0x1800a1460  push    rdi
0x1800a1461  sub     rsp, 28h
0x1800a1465  xor     edi, edi
0x1800a1467  mov     rbx, rdx
0x1800a146a  mov     esi, ecx
0x1800a146c  test    ecx, ecx
0x1800a146e  jz      short loc_1800A14A6
0x1800a1470  lea     rbp, [rdi+rdi*2]
0x1800a1474  mov     rcx, [rbx+rbp*8+10h]; pv
0x1800a1479  test    rcx, rcx
0x1800a147c  jz      short loc_1800A148A
0x1800a147e  call    cs:__imp_CoTaskMemFree
0x1800a1485  nop     dword ptr [rax+rax+00h]
0x1800a148a  mov     rcx, [rbx+rbp*8+8]; pv
0x1800a148f  test    rcx, rcx
0x1800a1492  jz      short loc_1800A14A0
0x1800a1494  call    cs:__imp_CoTaskMemFree
0x1800a149b  nop     dword ptr [rax+rax+00h]
0x1800a14a0  inc     edi
0x1800a14a2  cmp     edi, esi
0x1800a14a4  jb      short loc_1800A1470
0x1800a14a6  mov     rcx, rbx; pv
0x1800a14a9  call    cs:__imp_CoTaskMemFree
0x1800a14b0  nop     dword ptr [rax+rax+00h]
0x1800a14b5  add     rsp, 28h
0x1800a14b9  pop     rdi
0x1800a14ba  pop     rsi
0x1800a14bb  pop     rbp
0x1800a14bc  pop     rbx
0x1800a14bd  retn
```
