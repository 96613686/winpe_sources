# DsqFreeObject(tagDSServiceProps *,ulong,int)

- ea: `0x18009785c`
- end: `0x180097962`
- name: `?DsqFreeObject@@YAXPEAUtagDSServiceProps@@KH@Z`
- size: `262`
- prototype: `void __fastcall(struct tagDSServiceProps *, unsigned int, int)`
- caller_count: `6`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180071694`
- `0x180071cc0`
- `0x1800725d0`
- `0x180072850`
- `0x180072dd0`
- `0x180072ff0`

## callees

- `0x18009785c`
- `0x18009ae75`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180097880`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009788e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009789d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800978ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800978d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800978e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800978fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180097923`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009793c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180097880`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009788e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009789d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800978ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800978d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800978e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800978fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180097923`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009793c`

## pseudocode

```c
void __fastcall DsqFreeObject(struct tagDSServiceProps *a1)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  unsigned int i; // edi
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  __int64 j; // rdi
  void *v10; // rcx
  void *v11; // rcx

  if ( a1 )
  {
    v2 = (void *)*((_QWORD *)a1 + 7);
    if ( v2 )
      CoTaskMemFree(v2);
    if ( *(_QWORD *)a1 )
      CoTaskMemFree(*(LPVOID *)a1);
    v3 = (void *)*((_QWORD *)a1 + 1);
    if ( v3 )
      CoTaskMemFree(v3);
    v4 = (void *)*((_QWORD *)a1 + 2);
    if ( v4 )
      CoTaskMemFree(v4);
    if ( *((_QWORD *)a1 + 14) )
    {
      for ( i = 0; i < *((_DWORD *)a1 + 27); ++i )
      {
        v6 = *(void **)(*((_QWORD *)a1 + 14) + 16LL * i);
        if ( v6 )
          CoTaskMemFree(v6);
        v7 = *(void **)(*((_QWORD *)a1 + 14) + 16LL * i + 8);
        if ( v7 )
          CoTaskMemFree(v7);
      }
      v8 = (void *)*((_QWORD *)a1 + 14);
      if ( v8 )
        CoTaskMemFree(v8);
    }
    if ( *((_QWORD *)a1 + 16) )
    {
      for ( j = 0; (unsigned int)j < *((_DWORD *)a1 + 30); j = (unsigned int)(j + 1) )
      {
        v10 = *(void **)(*((_QWORD *)a1 + 16) + 8 * j);
        if ( v10 )
          CoTaskMemFree(v10);
      }
      v11 = (void *)*((_QWORD *)a1 + 16);
      if ( v11 )
        CoTaskMemFree(v11);
    }
    memset_0(a1, 0, 0x90u);
  }
}

```

## disassembly

```asm
0x18009785c  test    rcx, rcx
0x18009785f  jz      locret_180097961
0x180097865  mov     [rsp+arg_0], rbx
0x18009786a  mov     [rsp+arg_8], rsi
0x18009786f  push    rdi
0x180097870  sub     rsp, 20h
0x180097874  mov     rbx, rcx
0x180097877  mov     rcx, [rcx+38h]; pv
0x18009787b  test    rcx, rcx
0x18009787e  jz      short loc_180097886
0x180097880  call    cs:__imp_CoTaskMemFree
0x180097886  mov     rcx, [rbx]; pv
0x180097889  test    rcx, rcx
0x18009788c  jz      short loc_180097894
0x18009788e  call    cs:__imp_CoTaskMemFree
0x180097894  mov     rcx, [rbx+8]; pv
0x180097898  test    rcx, rcx
0x18009789b  jz      short loc_1800978A3
0x18009789d  call    cs:__imp_CoTaskMemFree
0x1800978a3  mov     rcx, [rbx+10h]; pv
0x1800978a7  test    rcx, rcx
0x1800978aa  jz      short loc_1800978B2
0x1800978ac  call    cs:__imp_CoTaskMemFree
0x1800978b2  cmp     qword ptr [rbx+70h], 0
0x1800978b7  jz      short loc_180097902
0x1800978b9  xor     edi, edi
0x1800978bb  cmp     [rbx+6Ch], edi
0x1800978be  jbe     short loc_1800978F3
0x1800978c0  mov     rax, [rbx+70h]
0x1800978c4  mov     esi, edi
0x1800978c6  add     rsi, rsi
0x1800978c9  mov     rcx, [rax+rsi*8]; pv
0x1800978cd  test    rcx, rcx
0x1800978d0  jz      short loc_1800978D8
0x1800978d2  call    cs:__imp_CoTaskMemFree
0x1800978d8  mov     rax, [rbx+70h]
0x1800978dc  mov     rcx, [rax+rsi*8+8]; pv
0x1800978e1  test    rcx, rcx
0x1800978e4  jz      short loc_1800978EC
0x1800978e6  call    cs:__imp_CoTaskMemFree
0x1800978ec  inc     edi
0x1800978ee  cmp     edi, [rbx+6Ch]
0x1800978f1  jb      short loc_1800978C0
0x1800978f3  mov     rcx, [rbx+70h]; pv
0x1800978f7  test    rcx, rcx
0x1800978fa  jz      short loc_180097902
0x1800978fc  call    cs:__imp_CoTaskMemFree
0x180097902  cmp     qword ptr [rbx+80h], 0
0x18009790a  jz      short loc_180097942
0x18009790c  xor     edi, edi
0x18009790e  cmp     [rbx+78h], edi
0x180097911  jbe     short loc_180097930
0x180097913  mov     rax, [rbx+80h]
0x18009791a  mov     rcx, [rax+rdi*8]; pv
0x18009791e  test    rcx, rcx
0x180097921  jz      short loc_180097929
0x180097923  call    cs:__imp_CoTaskMemFree
0x180097929  inc     edi
0x18009792b  cmp     edi, [rbx+78h]
0x18009792e  jb      short loc_180097913
0x180097930  mov     rcx, [rbx+80h]; pv
0x180097937  test    rcx, rcx
0x18009793a  jz      short loc_180097942
0x18009793c  call    cs:__imp_CoTaskMemFree
0x180097942  xor     edx, edx; Val
0x180097944  mov     r8d, 90h; Size
0x18009794a  mov     rcx, rbx; void *
0x18009794d  call    memset_0
0x180097952  mov     rbx, [rsp+28h+arg_0]
0x180097957  mov     rsi, [rsp+28h+arg_8]
0x18009795c  add     rsp, 20h
0x180097960  pop     rdi
0x180097961  retn
```
