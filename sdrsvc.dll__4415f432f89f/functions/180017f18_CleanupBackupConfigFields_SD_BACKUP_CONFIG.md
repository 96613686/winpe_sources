# CleanupBackupConfigFields(_SD_BACKUP_CONFIG *)

- ea: `0x180017f18`
- end: `0x180018133`
- name: `?CleanupBackupConfigFields@@YAJPEAU_SD_BACKUP_CONFIG@@@Z`
- size: `539`
- prototype: `__int64 __fastcall(struct _SD_BACKUP_CONFIG *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180012948`
- `0x180014184`

## callees

- `0x18001586c`
- `0x180015974`
- `0x180015fc4`
- `0x180017f18`
- `0x18001813c`
- `0x18002170a`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017f92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017fd2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017fec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018006`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018023`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018040`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018091`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001809c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800180e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800180fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017f92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017fd2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017fec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018006`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018023`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018040`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018091`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001809c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800180e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800180fd`

## string_xrefs

- `0x180017f2b`: `CleanupBackupConfigFields`

## pseudocode

```c
__int64 __fastcall CleanupBackupConfigFields(struct _SD_BACKUP_CONFIG *a1)
{
  LPVOID *v2; // rbx
  __int64 v3; // rsi
  _BYTE *v4; // rax
  __int64 v5; // rcx
  __int64 i; // rcx
  LPVOID *v7; // rbx
  _BYTE *v8; // rax
  __int64 j; // rsi
  LPVOID *v10; // rbx
  LPVOID *v11; // rbx
  LPVOID *v12; // rbx
  LPVOID *v13; // rbx
  __int64 v14; // rsi
  unsigned int v15; // r14d
  unsigned int k; // ebp
  __int64 v17; // rbx
  void *v18; // rcx
  unsigned int v19; // ebx
  int v21; // [rsp+20h] [rbp-A8h] BYREF
  __int16 v22; // [rsp+24h] [rbp-A4h]
  _DWORD v23[28]; // [rsp+58h] [rbp-70h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)v23, "CleanupBackupConfigFields", 275, 1);
  if ( a1 )
  {
    v2 = (LPVOID *)((char *)a1 + 200);
    v3 = -1;
    v4 = (_BYTE *)*((_QWORD *)a1 + 25);
    if ( v4 )
    {
      v5 = -1;
      do
        ++v5;
      while ( *(_WORD *)&v4[2 * v5] );
      for ( i = 2 * v5; i; --i )
        *v4++ = 0;
      if ( a1 != (struct _SD_BACKUP_CONFIG *)-200LL && *v2 )
      {
        CoTaskMemFree(*v2);
        *v2 = 0;
      }
    }
    v7 = (LPVOID *)((char *)a1 + 208);
    v8 = (_BYTE *)*((_QWORD *)a1 + 26);
    if ( v8 )
    {
      do
        ++v3;
      while ( *(_WORD *)&v8[2 * v3] );
      for ( j = 2 * v3; j; --j )
        *v8++ = 0;
      if ( a1 != (struct _SD_BACKUP_CONFIG *)-208LL && *v7 )
      {
        CoTaskMemFree(*v7);
        *v7 = 0;
      }
    }
    v10 = (LPVOID *)((char *)a1 + 8);
    if ( a1 != (struct _SD_BACKUP_CONFIG *)-8LL && *v10 )
    {
      CoTaskMemFree(*v10);
      *v10 = 0;
    }
    v11 = (LPVOID *)((char *)a1 + 16);
    if ( a1 != (struct _SD_BACKUP_CONFIG *)-16LL && *v11 )
    {
      CoTaskMemFree(*v11);
      *v11 = 0;
    }
    v12 = (LPVOID *)((char *)a1 + 216);
    if ( a1 != (struct _SD_BACKUP_CONFIG *)-216LL && *v12 )
    {
      CoTaskMemFree(*v12);
      *v12 = 0;
    }
    v13 = (LPVOID *)((char *)a1 + 224);
    if ( a1 != (struct _SD_BACKUP_CONFIG *)-224LL && *v13 )
    {
      CoTaskMemFree(*v13);
      *v13 = 0;
    }
    CleanupStorageDeviceProp((struct _SD_BACKUP_CONFIG *)((char *)a1 + 40));
    v14 = *((_QWORD *)a1 + 4);
    v15 = *((_DWORD *)a1 + 6);
    CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v21, "CleanupBackupRoots", 35, 1);
    if ( v15 && v14 )
    {
      for ( k = 0; k < v15; ++k )
      {
        v17 = 3LL * k;
        CoTaskMemFree(*(LPVOID *)(v14 + 24LL * k));
        CoTaskMemFree(*(LPVOID *)(v14 + 24LL * k + 8));
        *(_OWORD *)(v14 + 8 * v17) = 0;
        *(_QWORD *)(v14 + 8 * v17 + 16) = 0;
      }
    }
    else
    {
      v21 = 0;
      v22 = 42;
    }
    CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v21);
    CleanupBackupUsers(*((_DWORD *)a1 + 48), *((struct _SD_BACKUP_USER_DATA **)a1 + 23));
    CoTaskMemFree(*((LPVOID *)a1 + 4));
    v18 = (void *)*((_QWORD *)a1 + 23);
    *((_DWORD *)a1 + 6) = 0;
    *((_QWORD *)a1 + 4) = 0;
    CoTaskMemFree(v18);
    memset_0(a1, 0, 0xF8u);
  }
  v19 = v23[0];
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)v23);
  return v19;
}

```

## disassembly

```asm
0x180017f18  push    rbx
0x180017f1a  push    rbp
0x180017f1b  push    rsi
0x180017f1c  push    rdi
0x180017f1d  push    r14
0x180017f1f  push    r15
0x180017f21  sub     rsp, 98h
0x180017f28  mov     rdi, rcx
0x180017f2b  lea     rdx, aCleanupbackupc; "CleanupBackupConfigFields"
0x180017f32  lea     rcx, [rsp+0C8h+var_70]; this
0x180017f37  mov     r9d, 1; unsigned __int16
0x180017f3d  mov     r8d, 113h; unsigned __int16
0x180017f43  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180017f48  xor     r15d, r15d
0x180017f4b  test    rdi, rdi
0x180017f4e  jz      loc_180018113
0x180017f54  lea     rbx, [rdi+0C8h]
0x180017f5b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180017f5f  mov     rax, [rbx]
0x180017f62  test    rax, rax
0x180017f65  jz      short loc_180017F9B
0x180017f67  mov     rcx, rsi
0x180017f6a  inc     rcx
0x180017f6d  cmp     [rax+rcx*2], r15w
0x180017f72  jnz     short loc_180017F6A
0x180017f74  add     rcx, rcx
0x180017f77  jz      short loc_180017F85
0x180017f79  mov     [rax], r15b
0x180017f7c  inc     rax
0x180017f7f  sub     rcx, 1
0x180017f83  jnz     short loc_180017F79
0x180017f85  test    rbx, rbx
0x180017f88  jz      short loc_180017F9B
0x180017f8a  mov     rcx, [rbx]; pv
0x180017f8d  test    rcx, rcx
0x180017f90  jz      short loc_180017F9B
0x180017f92  call    cs:__imp_CoTaskMemFree
0x180017f98  mov     [rbx], r15
0x180017f9b  lea     rbx, [rdi+0D0h]
0x180017fa2  mov     rax, [rbx]
0x180017fa5  test    rax, rax
0x180017fa8  jz      short loc_180017FDB
0x180017faa  inc     rsi
0x180017fad  cmp     [rax+rsi*2], r15w
0x180017fb2  jnz     short loc_180017FAA
0x180017fb4  add     rsi, rsi
0x180017fb7  jz      short loc_180017FC5
0x180017fb9  mov     [rax], r15b
0x180017fbc  inc     rax
0x180017fbf  sub     rsi, 1
0x180017fc3  jnz     short loc_180017FB9
0x180017fc5  test    rbx, rbx
0x180017fc8  jz      short loc_180017FDB
0x180017fca  mov     rcx, [rbx]; pv
0x180017fcd  test    rcx, rcx
0x180017fd0  jz      short loc_180017FDB
0x180017fd2  call    cs:__imp_CoTaskMemFree
0x180017fd8  mov     [rbx], r15
0x180017fdb  lea     rbx, [rdi+8]
0x180017fdf  test    rbx, rbx
0x180017fe2  jz      short loc_180017FF5
0x180017fe4  mov     rcx, [rbx]; pv
0x180017fe7  test    rcx, rcx
0x180017fea  jz      short loc_180017FF5
0x180017fec  call    cs:__imp_CoTaskMemFree
0x180017ff2  mov     [rbx], r15
0x180017ff5  lea     rbx, [rdi+10h]
0x180017ff9  test    rbx, rbx
0x180017ffc  jz      short loc_18001800F
0x180017ffe  mov     rcx, [rbx]; pv
0x180018001  test    rcx, rcx
0x180018004  jz      short loc_18001800F
0x180018006  call    cs:__imp_CoTaskMemFree
0x18001800c  mov     [rbx], r15
0x18001800f  lea     rbx, [rdi+0D8h]
0x180018016  test    rbx, rbx
0x180018019  jz      short loc_18001802C
0x18001801b  mov     rcx, [rbx]; pv
0x18001801e  test    rcx, rcx
0x180018021  jz      short loc_18001802C
0x180018023  call    cs:__imp_CoTaskMemFree
0x180018029  mov     [rbx], r15
0x18001802c  lea     rbx, [rdi+0E0h]
0x180018033  test    rbx, rbx
0x180018036  jz      short loc_180018049
0x180018038  mov     rcx, [rbx]; pv
0x18001803b  test    rcx, rcx
0x18001803e  jz      short loc_180018049
0x180018040  call    cs:__imp_CoTaskMemFree
0x180018046  mov     [rbx], r15
0x180018049  lea     rcx, [rdi+28h]; struct _SD_STORAGE_DEVICE_PROP *
0x18001804d  call    ?CleanupStorageDeviceProp@@YAXPEAU_SD_STORAGE_DEVICE_PROP@@@Z; CleanupStorageDeviceProp(_SD_STORAGE_DEVICE_PROP *)
0x180018052  mov     rsi, [rdi+20h]
0x180018056  lea     rdx, aCleanupbackupr; "CleanupBackupRoots"
0x18001805d  mov     r14d, [rdi+18h]
0x180018061  lea     rcx, [rsp+0C8h+var_A8]; this
0x180018066  mov     r9d, 1; unsigned __int16
0x18001806c  lea     r8d, [r9+22h]; unsigned __int16
0x180018070  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180018075  test    r14d, r14d
0x180018078  jz      short loc_1800180B9
0x18001807a  test    rsi, rsi
0x18001807d  jz      short loc_1800180B9
0x18001807f  mov     ebp, r15d
0x180018082  test    r14d, r14d
0x180018085  jz      short loc_1800180C8
0x180018087  mov     eax, ebp
0x180018089  lea     rbx, [rax+rax*2]
0x18001808d  mov     rcx, [rsi+rbx*8]; pv
0x180018091  call    cs:__imp_CoTaskMemFree
0x180018097  mov     rcx, [rsi+rbx*8+8]; pv
0x18001809c  call    cs:__imp_CoTaskMemFree
0x1800180a2  xor     eax, eax
0x1800180a4  xorps   xmm0, xmm0
0x1800180a7  inc     ebp
0x1800180a9  movups  xmmword ptr [rsi+rbx*8], xmm0
0x1800180ad  mov     [rsi+rbx*8+10h], rax
0x1800180b2  cmp     ebp, r14d
0x1800180b5  jb      short loc_180018087
0x1800180b7  jmp     short loc_1800180C8
0x1800180b9  mov     eax, 2Ah ; '*'
0x1800180be  mov     [rsp+0C8h+var_A8], r15d
0x1800180c3  mov     [rsp+0C8h+var_A4], ax
0x1800180c8  lea     rcx, [rsp+0C8h+var_A8]; this
0x1800180cd  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800180d2  mov     rdx, [rdi+0B8h]; struct _SD_BACKUP_USER_DATA *
0x1800180d9  mov     ecx, [rdi+0C0h]; unsigned int
0x1800180df  call    ?CleanupBackupUsers@@YAJKPEAU_SD_BACKUP_USER_DATA@@@Z; CleanupBackupUsers(ulong,_SD_BACKUP_USER_DATA *)
0x1800180e4  mov     rcx, [rdi+20h]; pv
0x1800180e8  call    cs:__imp_CoTaskMemFree
0x1800180ee  mov     rcx, [rdi+0B8h]; pv
0x1800180f5  mov     [rdi+18h], r15d
0x1800180f9  mov     [rdi+20h], r15
0x1800180fd  call    cs:__imp_CoTaskMemFree
0x180018103  xor     edx, edx; Val
0x180018105  mov     r8d, 0F8h; Size
0x18001810b  mov     rcx, rdi; void *
0x18001810e  call    memset_0
0x180018113  mov     ebx, [rsp+0C8h+var_70]
0x180018117  lea     rcx, [rsp+0C8h+var_70]; this
0x18001811c  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180018121  mov     eax, ebx
0x180018123  add     rsp, 98h
0x18001812a  pop     r15
0x18001812c  pop     r14
0x18001812e  pop     rdi
0x18001812f  pop     rsi
0x180018130  pop     rbp
0x180018131  pop     rbx
0x180018132  retn
```
