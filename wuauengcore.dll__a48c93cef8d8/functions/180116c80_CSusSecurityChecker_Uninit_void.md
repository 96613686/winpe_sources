# CSusSecurityChecker::Uninit(void)

- ea: `0x180116c80`
- end: `0x180116d84`
- name: `?Uninit@CSusSecurityChecker@@QEAAXXZ`
- size: `260`
- prototype: `void __fastcall(CSusSecurityChecker *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180013b6c`
- `0x1800142a0`
- `0x1800466d0`
- `0x180116ad4`
- `0x18011b58c`
- `0x1801cfab0`
- `0x180212d00`

## callees

- `0x180116c80`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180116c96`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180116cad`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180116cc4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180116cdb`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180116cf2`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180116d09`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180116d20`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180116d37`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180116d4e`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180116c96`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180116cad`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180116cc4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180116cdb`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180116cf2`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180116d09`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180116d20`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180116d37`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180116d4e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180116d62`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180116d62`

## pseudocode

```c
void __fastcall CSusSecurityChecker::Uninit(CSusSecurityChecker *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  __int64 i; // rdi

  v2 = (void *)*((_QWORD *)this + 8);
  if ( v2 )
    FreeSid(v2);
  *((_QWORD *)this + 8) = 0;
  v3 = (void *)*((_QWORD *)this + 9);
  if ( v3 )
    FreeSid(v3);
  *((_QWORD *)this + 9) = 0;
  v4 = (void *)*((_QWORD *)this + 10);
  if ( v4 )
    FreeSid(v4);
  *((_QWORD *)this + 10) = 0;
  v5 = (void *)*((_QWORD *)this + 6);
  if ( v5 )
    FreeSid(v5);
  *((_QWORD *)this + 6) = 0;
  v6 = (void *)*((_QWORD *)this + 7);
  if ( v6 )
    FreeSid(v6);
  *((_QWORD *)this + 7) = 0;
  v7 = (void *)*((_QWORD *)this + 11);
  if ( v7 )
    FreeSid(v7);
  *((_QWORD *)this + 11) = 0;
  v8 = (void *)*((_QWORD *)this + 5);
  if ( v8 )
    FreeSid(v8);
  *((_QWORD *)this + 5) = 0;
  v9 = (void *)*((_QWORD *)this + 12);
  if ( v9 )
    FreeSid(v9);
  *((_QWORD *)this + 12) = 0;
  v10 = (void *)*((_QWORD *)this + 13);
  if ( v10 )
    FreeSid(v10);
  *((_QWORD *)this + 13) = 0;
  for ( i = 0; i < 5; ++i )
  {
    LocalFree(*((HLOCAL *)this + i));
    *((_QWORD *)this + i) = 0;
  }
}

```

## disassembly

```asm
0x180116c80  mov     [rsp+arg_0], rbx
0x180116c85  push    rdi
0x180116c86  sub     rsp, 20h
0x180116c8a  mov     rbx, rcx
0x180116c8d  mov     rcx, [rcx+40h]; pSid
0x180116c91  test    rcx, rcx
0x180116c94  jz      short loc_180116C9C
0x180116c96  call    cs:__imp_FreeSid
0x180116c9c  mov     qword ptr [rbx+40h], 0
0x180116ca4  mov     rcx, [rbx+48h]; pSid
0x180116ca8  test    rcx, rcx
0x180116cab  jz      short loc_180116CB3
0x180116cad  call    cs:__imp_FreeSid
0x180116cb3  mov     qword ptr [rbx+48h], 0
0x180116cbb  mov     rcx, [rbx+50h]; pSid
0x180116cbf  test    rcx, rcx
0x180116cc2  jz      short loc_180116CCA
0x180116cc4  call    cs:__imp_FreeSid
0x180116cca  mov     qword ptr [rbx+50h], 0
0x180116cd2  mov     rcx, [rbx+30h]; pSid
0x180116cd6  test    rcx, rcx
0x180116cd9  jz      short loc_180116CE1
0x180116cdb  call    cs:__imp_FreeSid
0x180116ce1  mov     qword ptr [rbx+30h], 0
0x180116ce9  mov     rcx, [rbx+38h]; pSid
0x180116ced  test    rcx, rcx
0x180116cf0  jz      short loc_180116CF8
0x180116cf2  call    cs:__imp_FreeSid
0x180116cf8  mov     qword ptr [rbx+38h], 0
0x180116d00  mov     rcx, [rbx+58h]; pSid
0x180116d04  test    rcx, rcx
0x180116d07  jz      short loc_180116D0F
0x180116d09  call    cs:__imp_FreeSid
0x180116d0f  mov     qword ptr [rbx+58h], 0
0x180116d17  mov     rcx, [rbx+28h]; pSid
0x180116d1b  test    rcx, rcx
0x180116d1e  jz      short loc_180116D26
0x180116d20  call    cs:__imp_FreeSid
0x180116d26  mov     qword ptr [rbx+28h], 0
0x180116d2e  mov     rcx, [rbx+60h]; pSid
0x180116d32  test    rcx, rcx
0x180116d35  jz      short loc_180116D3D
0x180116d37  call    cs:__imp_FreeSid
0x180116d3d  mov     qword ptr [rbx+60h], 0
0x180116d45  mov     rcx, [rbx+68h]; pSid
0x180116d49  test    rcx, rcx
0x180116d4c  jz      short loc_180116D54
0x180116d4e  call    cs:__imp_FreeSid
0x180116d54  mov     qword ptr [rbx+68h], 0
0x180116d5c  xor     edi, edi
0x180116d5e  mov     rcx, [rbx+rdi*8]; hMem
0x180116d62  call    cs:__imp_LocalFree
0x180116d68  mov     qword ptr [rbx+rdi*8], 0
0x180116d70  inc     rdi
0x180116d73  cmp     rdi, 5
0x180116d77  jl      short loc_180116D5E
0x180116d79  mov     rbx, [rsp+28h+arg_0]
0x180116d7e  add     rsp, 20h
0x180116d82  pop     rdi
0x180116d83  retn
```
