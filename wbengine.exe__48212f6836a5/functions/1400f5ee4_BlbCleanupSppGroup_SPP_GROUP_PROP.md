# BlbCleanupSppGroup(_SPP_GROUP_PROP *)

- ea: `0x1400f5ee4`
- end: `0x1400f5feb`
- name: `?BlbCleanupSppGroup@@YAXPEAU_SPP_GROUP_PROP@@@Z`
- size: `263`
- prototype: `void __fastcall(struct _SPP_GROUP_PROP *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1400249b8`
- `0x1400f613c`

## callees

- `0x140006ca8`
- `0x1400f5ee4`
- `0x1400f6834`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1400f5f18`
- `ole32!CoTaskMemFree` at `0x1400f5f27`
- `ole32!CoTaskMemFree` at `0x1400f5f36`
- `ole32!CoTaskMemFree` at `0x1400f5f45`
- `ole32!CoTaskMemFree` at `0x1400f5f6d`
- `ole32!CoTaskMemFree` at `0x1400f5f7d`
- `ole32!CoTaskMemFree` at `0x1400f5fa3`
- `ole32!CoTaskMemFree` at `0x1400f5fb8`
- `ole32!CoTaskMemFree` at `0x1400f5fc9`
- `ole32!CoTaskMemFree` at `0x1400f5f18`
- `ole32!CoTaskMemFree` at `0x1400f5f27`
- `ole32!CoTaskMemFree` at `0x1400f5f36`
- `ole32!CoTaskMemFree` at `0x1400f5f45`
- `ole32!CoTaskMemFree` at `0x1400f5f6d`
- `ole32!CoTaskMemFree` at `0x1400f5f7d`
- `ole32!CoTaskMemFree` at `0x1400f5fa3`
- `ole32!CoTaskMemFree` at `0x1400f5fb8`
- `ole32!CoTaskMemFree` at `0x1400f5fc9`

## pseudocode

```c
void __fastcall BlbCleanupSppGroup(struct _SPP_GROUP_PROP *a1)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  unsigned int i; // ebp
  __int64 v7; // rsi
  __int64 v8; // rdi
  void *v9; // rcx
  void *v10; // rcx
  __int64 j; // r14
  void *v12; // rcx
  struct _SPP_CLIENT_PROP *v13; // rdx

  if ( !a1 )
    BlbAssert("base\\stor\\blb\\engine\\blbengutils\\blbspputils.cpp", 0x125u, "pGroup");
  v2 = (void *)*((_QWORD *)a1 + 4);
  if ( v2 )
    CoTaskMemFree(v2);
  v3 = (void *)*((_QWORD *)a1 + 7);
  if ( v3 )
    CoTaskMemFree(v3);
  v4 = (void *)*((_QWORD *)a1 + 8);
  if ( v4 )
    CoTaskMemFree(v4);
  v5 = (void *)*((_QWORD *)a1 + 9);
  if ( v5 )
    CoTaskMemFree(v5);
  if ( *((_QWORD *)a1 + 11) )
  {
    for ( i = 0; i < *((_DWORD *)a1 + 20); ++i )
    {
      v7 = *((_QWORD *)a1 + 11);
      v8 = 56LL * i;
      v9 = *(void **)(v8 + v7 + 16);
      if ( v9 )
        CoTaskMemFree(v9);
      v10 = *(void **)(v8 + v7 + 24);
      if ( v10 )
        CoTaskMemFree(v10);
      if ( *(_QWORD *)(v8 + v7 + 40) )
      {
        for ( j = 0; (unsigned int)j < *(_DWORD *)(v8 + v7 + 32); j = (unsigned int)(j + 1) )
        {
          v12 = *(void **)(*(_QWORD *)(v8 + v7 + 40) + 8 * j);
          if ( v12 )
            CoTaskMemFree(v12);
        }
        CoTaskMemFree(*(LPVOID *)(v8 + v7 + 40));
      }
    }
    CoTaskMemFree(*((LPVOID *)a1 + 11));
  }
  v13 = (struct _SPP_CLIENT_PROP *)*((_QWORD *)a1 + 13);
  if ( v13 )
    BlbFreeSppClientArray(*((_DWORD *)a1 + 24), v13);
}

```

## disassembly

```asm
0x1400f5ee4  push    rbx
0x1400f5ee6  push    rbp
0x1400f5ee7  push    rsi
0x1400f5ee8  push    rdi
0x1400f5ee9  push    r14
0x1400f5eeb  sub     rsp, 20h
0x1400f5eef  mov     rbx, rcx
0x1400f5ef2  test    rcx, rcx
0x1400f5ef5  jnz     short loc_1400F5F0F
0x1400f5ef7  lea     r8, aPgroup; "pGroup"
0x1400f5efe  mov     edx, 125h; unsigned int
0x1400f5f03  lea     rcx, aBaseStorBlbEng_25; "base\\stor\\blb\\engine\\blbengutils\\b"...
0x1400f5f0a  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400f5f0f  mov     rcx, [rbx+20h]; pv
0x1400f5f13  test    rcx, rcx
0x1400f5f16  jz      short loc_1400F5F1E
0x1400f5f18  call    cs:__imp_CoTaskMemFree
0x1400f5f1e  mov     rcx, [rbx+38h]; pv
0x1400f5f22  test    rcx, rcx
0x1400f5f25  jz      short loc_1400F5F2D
0x1400f5f27  call    cs:__imp_CoTaskMemFree
0x1400f5f2d  mov     rcx, [rbx+40h]; pv
0x1400f5f31  test    rcx, rcx
0x1400f5f34  jz      short loc_1400F5F3C
0x1400f5f36  call    cs:__imp_CoTaskMemFree
0x1400f5f3c  mov     rcx, [rbx+48h]; pv
0x1400f5f40  test    rcx, rcx
0x1400f5f43  jz      short loc_1400F5F4B
0x1400f5f45  call    cs:__imp_CoTaskMemFree
0x1400f5f4b  cmp     qword ptr [rbx+58h], 0
0x1400f5f50  jz      short loc_1400F5FCF
0x1400f5f52  xor     ebp, ebp
0x1400f5f54  cmp     [rbx+50h], ebp
0x1400f5f57  jbe     short loc_1400F5FC5
0x1400f5f59  mov     rsi, [rbx+58h]
0x1400f5f5d  mov     eax, ebp
0x1400f5f5f  imul    rdi, rax, 38h ; '8'
0x1400f5f63  mov     rcx, [rdi+rsi+10h]; pv
0x1400f5f68  test    rcx, rcx
0x1400f5f6b  jz      short loc_1400F5F73
0x1400f5f6d  call    cs:__imp_CoTaskMemFree
0x1400f5f73  mov     rcx, [rdi+rsi+18h]; pv
0x1400f5f78  test    rcx, rcx
0x1400f5f7b  jz      short loc_1400F5F83
0x1400f5f7d  call    cs:__imp_CoTaskMemFree
0x1400f5f83  cmp     qword ptr [rdi+rsi+28h], 0
0x1400f5f89  jz      short loc_1400F5FBE
0x1400f5f8b  xor     r14d, r14d
0x1400f5f8e  cmp     [rdi+rsi+20h], r14d
0x1400f5f93  jbe     short loc_1400F5FB3
0x1400f5f95  mov     rax, [rdi+rsi+28h]
0x1400f5f9a  mov     rcx, [rax+r14*8]; pv
0x1400f5f9e  test    rcx, rcx
0x1400f5fa1  jz      short loc_1400F5FA9
0x1400f5fa3  call    cs:__imp_CoTaskMemFree
0x1400f5fa9  inc     r14d
0x1400f5fac  cmp     r14d, [rdi+rsi+20h]
0x1400f5fb1  jb      short loc_1400F5F95
0x1400f5fb3  mov     rcx, [rdi+rsi+28h]; pv
0x1400f5fb8  call    cs:__imp_CoTaskMemFree
0x1400f5fbe  inc     ebp
0x1400f5fc0  cmp     ebp, [rbx+50h]
0x1400f5fc3  jb      short loc_1400F5F59
0x1400f5fc5  mov     rcx, [rbx+58h]; pv
0x1400f5fc9  call    cs:__imp_CoTaskMemFree
0x1400f5fcf  mov     rdx, [rbx+68h]; struct _SPP_CLIENT_PROP *
0x1400f5fd3  test    rdx, rdx
0x1400f5fd6  jz      short loc_1400F5FE0
0x1400f5fd8  mov     ecx, [rbx+60h]; unsigned int
0x1400f5fdb  call    ?BlbFreeSppClientArray@@YAXKPEAU_SPP_CLIENT_PROP@@@Z; BlbFreeSppClientArray(ulong,_SPP_CLIENT_PROP *)
0x1400f5fe0  add     rsp, 20h
0x1400f5fe4  pop     r14
0x1400f5fe6  pop     rdi
0x1400f5fe7  pop     rsi
0x1400f5fe8  pop     rbp
0x1400f5fe9  pop     rbx
0x1400f5fea  retn
```
