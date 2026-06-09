# CRegistrySource::QueryValueDirect(ushort const *,ushort const *,_FLAGGED_BYTE_BLOB * *)

- ea: `0x1800085a0`
- end: `0x180008757`
- name: `?QueryValueDirect@CRegistrySource@@UEAAJPEBG0PEAPEAU_FLAGGED_BYTE_BLOB@@@Z`
- size: `439`
- prototype: `int(CRegistrySource *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct _FLAGGED_BYTE_BLOB **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800083d0`
- `0x1800085a0`
- `0x18005d538`
- `0x180066910`
- `0x18009341c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800086e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800086e1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000860c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008728`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000860c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008728`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000868f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000868f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000873b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000873b`

## pseudocode

```c
__int64 __fastcall CRegistrySource::QueryValueDirect(
        CRegistrySource *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct _FLAGGED_BYTE_BLOB **a4)
{
  HKEY v5; // rcx
  LSTATUS v8; // eax
  void *v9; // rcx
  int v10; // ebx
  ULONG v12; // esi
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[256]; // [rsp+40h] [rbp-C0h] BYREF

  cbData = 256;
  Type = 0;
  v5 = (HKEY)*((_QWORD *)this + 6);
  phkResult = v5;
  *a4 = 0;
  if ( a2 && *a2 )
  {
    v10 = -2147467259;
    if ( RegOpenKeyExW(*((HKEY *)this + 6), a2, 0, 1u, &phkResult) )
      return (unsigned int)v10;
    v5 = phkResult;
  }
  v8 = RegQueryValueExW(v5, a3, 0, &Type, Data, &cbData);
  v10 = v8;
  if ( !v8 )
  {
    v12 = cbData;
    v10 = CTCoAllocPolicy::Alloc(v9, 1u, cbData + 8, (void **)a4);
    if ( v10 >= 0 )
    {
      (*a4)->clSize = v12;
      memcpy_0((*a4)->abData, Data, v12);
    }
    goto LABEL_6;
  }
  if ( v8 == 234 )
  {
    if ( (int)_SHAllocBlob(cbData, 0, a4) < 0 )
      goto LABEL_5;
    v10 = RegQueryValueExW(phkResult, a3, 0, &Type, (*a4)->abData, &cbData);
    if ( v10 )
    {
      CoTaskMemFree(*a4);
      *a4 = 0;
    }
  }
  if ( v10 > 0 )
LABEL_5:
    v10 = (unsigned __int16)v10 | 0x80070000;
LABEL_6:
  if ( phkResult != *((HKEY *)this + 6) )
    RegCloseKey(phkResult);
  if ( v10 >= 0 )
    (*a4)->fFlags = Type;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800085a0  push    rbp
0x1800085a2  push    rbx
0x1800085a3  push    rsi
0x1800085a4  push    rdi
0x1800085a5  push    r14
0x1800085a7  push    r15
0x1800085a9  lea     rbp, [rsp-58h]
0x1800085ae  sub     rsp, 158h
0x1800085b5  mov     rax, cs:__security_cookie
0x1800085bc  xor     rax, rsp
0x1800085bf  mov     [rbp+80h+var_40], rax
0x1800085c3  xor     r15d, r15d
0x1800085c6  mov     [rsp+180h+cbData], 100h
0x1800085ce  mov     [rsp+180h+Type], r15d
0x1800085d3  mov     r14, rcx
0x1800085d6  mov     rcx, [rcx+30h]; hKey
0x1800085da  mov     rdi, r9
0x1800085dd  mov     [rsp+180h+phkResult], rcx
0x1800085e2  mov     rsi, r8
0x1800085e5  mov     [r9], r15
0x1800085e8  test    rdx, rdx
0x1800085eb  jnz     short loc_180008669
0x1800085ed  lea     rax, [rsp+180h+cbData]
0x1800085f2  xor     r8d, r8d; lpReserved
0x1800085f5  mov     [rsp+180h+lpcbData], rax; lpcbData
0x1800085fa  lea     r9, [rsp+180h+Type]; lpType
0x1800085ff  lea     rax, [rsp+180h+Data]
0x180008604  mov     rdx, rsi; lpValueName
0x180008607  mov     [rsp+180h+lpData], rax; lpData
0x18000860c  call    cs:__imp_RegQueryValueExW
0x180008612  mov     ebx, eax
0x180008614  test    eax, eax
0x180008616  jz      loc_1800086A3
0x18000861c  cmp     eax, 0EAh
0x180008621  jz      loc_1800086EC
0x180008627  test    ebx, ebx
0x180008629  jle     short loc_180008634
0x18000862b  movzx   ebx, bx
0x18000862e  or      ebx, 80070000h
0x180008634  mov     rcx, [rsp+180h+phkResult]; hKey
0x180008639  cmp     rcx, [r14+30h]
0x18000863d  jnz     loc_1800086E1
0x180008643  test    ebx, ebx
0x180008645  jns     loc_180008749
0x18000864b  mov     eax, ebx
0x18000864d  mov     rcx, [rbp+80h+var_40]
0x180008651  xor     rcx, rsp; StackCookie
0x180008654  call    __security_check_cookie
0x180008659  add     rsp, 158h
0x180008660  pop     r15
0x180008662  pop     r14
0x180008664  pop     rdi
0x180008665  pop     rsi
0x180008666  pop     rbx
0x180008667  pop     rbp
0x180008668  retn
0x180008669  cmp     [rdx], r15w
0x18000866d  jz      loc_1800085ED
0x180008673  mov     rcx, [r14+30h]; hKey
0x180008677  lea     rax, [rsp+180h+phkResult]
0x18000867c  mov     r9d, 1; samDesired
0x180008682  mov     [rsp+180h+lpData], rax; phkResult
0x180008687  xor     r8d, r8d; ulOptions
0x18000868a  mov     ebx, 80004005h
0x18000868f  call    cs:__imp_RegOpenKeyExW
0x180008695  test    eax, eax
0x180008697  jnz     short loc_18000864B
0x180008699  mov     rcx, [rsp+180h+phkResult]
0x18000869e  jmp     loc_1800085ED
0x1800086a3  mov     esi, [rsp+180h+cbData]
0x1800086a7  mov     r9, rdi; void **
0x1800086aa  mov     edx, 1; unsigned int
0x1800086af  lea     r8d, [rsi+8]; unsigned __int64
0x1800086b3  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800086b8  mov     ebx, eax
0x1800086ba  test    eax, eax
0x1800086bc  js      loc_180008634
0x1800086c2  mov     rax, [rdi]
0x1800086c5  lea     rdx, [rsp+180h+Data]; Src
0x1800086ca  mov     r8d, esi; Size
0x1800086cd  mov     [rax+4], esi
0x1800086d0  mov     rcx, [rdi]
0x1800086d3  add     rcx, 8; void *
0x1800086d7  call    memcpy_0
0x1800086dc  jmp     loc_180008634
0x1800086e1  call    cs:__imp_RegCloseKey
0x1800086e7  jmp     loc_180008643
0x1800086ec  mov     ecx, [rsp+180h+cbData]; Size
0x1800086f0  mov     r8, rdi; struct _FLAGGED_BYTE_BLOB **
0x1800086f3  xor     edx, edx; Src
0x1800086f5  call    ?_SHAllocBlob@@YAJKPEAEPEAPEAU_FLAGGED_BYTE_BLOB@@@Z; _SHAllocBlob(ulong,uchar *,_FLAGGED_BYTE_BLOB * *)
0x1800086fa  test    eax, eax
0x1800086fc  js      loc_18000862B
0x180008702  mov     rax, [rdi]
0x180008705  lea     rcx, [rsp+180h+cbData]
0x18000870a  mov     [rsp+180h+lpcbData], rcx; lpcbData
0x18000870f  lea     r9, [rsp+180h+Type]; lpType
0x180008714  mov     rcx, [rsp+180h+phkResult]; hKey
0x180008719  add     rax, 8
0x18000871d  xor     r8d, r8d; lpReserved
0x180008720  mov     [rsp+180h+lpData], rax; lpData
0x180008725  mov     rdx, rsi; lpValueName
0x180008728  call    cs:__imp_RegQueryValueExW
0x18000872e  mov     ebx, eax
0x180008730  test    eax, eax
0x180008732  jz      loc_180008627
0x180008738  mov     rcx, [rdi]; pv
0x18000873b  call    cs:__imp_CoTaskMemFree
0x180008741  mov     [rdi], r15
0x180008744  jmp     loc_180008627
0x180008749  mov     rdx, [rdi]
0x18000874c  mov     ecx, [rsp+180h+Type]
0x180008750  mov     [rdx], ecx
0x180008752  jmp     loc_18000864B
```
