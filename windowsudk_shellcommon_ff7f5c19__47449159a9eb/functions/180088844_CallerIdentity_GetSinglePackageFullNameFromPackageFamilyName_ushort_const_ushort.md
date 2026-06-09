# CallerIdentity::GetSinglePackageFullNameFromPackageFamilyName(ushort const *,ushort * *)

- ea: `0x180088844`
- end: `0x18008899c`
- name: `?GetSinglePackageFullNameFromPackageFamilyName@CallerIdentity@@YAJPEBGPEAPEAG@Z`
- size: `344`
- prototype: `__int64 __fastcall(PCWSTR packageFamilyName, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004766c`

## callees

- `0x180088844`
- `0x1800889a4`
- `0x1800889dc`
- `0x180088a44`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008893e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180088947`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008893e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180088947`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackagesByPackageFamily` at `0x18008887f`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackagesByPackageFamily` at `0x180088905`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackagesByPackageFamily` at `0x18008887f`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackagesByPackageFamily` at `0x180088905`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetSinglePackageFullNameFromPackageFamilyName(
        PCWSTR packageFamilyName,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  int PackagesByPackageFamily; // eax
  __int64 v5; // rcx
  bool v6; // sf
  int v7; // eax
  void *v8; // rcx
  WCHAR *buffer; // rdi
  signed int v10; // esi
  WCHAR *v11; // rbx
  LONG v12; // eax
  __int64 v13; // r9
  int v15; // eax
  UINT32 count; // [rsp+88h] [rbp+48h] BYREF
  UINT32 bufferLength; // [rsp+90h] [rbp+50h] BYREF
  WCHAR *v18; // [rsp+98h] [rbp+58h] BYREF

  *(_QWORD *)a2 = 0;
  count = 0;
  bufferLength = 0;
  PackagesByPackageFamily = GetPackagesByPackageFamily(packageFamilyName, &count, 0, &bufferLength, 0);
  v6 = PackagesByPackageFamily < 0;
  if ( PackagesByPackageFamily > 0 )
  {
    PackagesByPackageFamily = (unsigned __int16)PackagesByPackageFamily | 0x80070000;
    v6 = PackagesByPackageFamily < 0;
  }
  if ( !v6 )
  {
    if ( !count )
      return (unsigned int)-2147023728;
    return (unsigned int)-2147418113;
  }
  if ( PackagesByPackageFamily != -2147024774 )
    return (unsigned int)-2147418113;
  v18 = 0;
  v7 = _AllocArray<unsigned short,CTCoAllocPolicy>(v5, 1, bufferLength, &v18);
  buffer = v18;
  v10 = v7;
  if ( v7 >= 0 )
  {
    v11 = 0;
    v18 = 0;
    if ( count == 1 )
    {
      if ( is_mul_ok(1u, 8u) )
      {
        v15 = CTCoAllocPolicy::Alloc(v8, 1u, 8u, (void **)&v18);
        v11 = v18;
        v10 = v15;
      }
      else
      {
        v10 = -2147024362;
      }
      if ( v10 >= 0 )
      {
        v12 = GetPackagesByPackageFamily(packageFamilyName, &count, (PWSTR *)v11, &bufferLength, buffer);
        v10 = v12;
        if ( v12 > 0 )
          v10 = (unsigned __int16)v12 | 0x80070000;
        if ( v10 >= 0 )
        {
          v13 = -1;
          do
            ++v13;
          while ( *(_WORD *)(*(_QWORD *)v11 + 2 * v13) );
          v10 = _AllocStringWorker<CTCoAllocPolicy>();
        }
      }
    }
    else
    {
      v10 = -2147418113;
    }
    CoTaskMemFree(v11);
  }
  CoTaskMemFree(buffer);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180088844  mov     [rsp-38h+arg_0], rbx
0x180088849  push    rbp
0x18008884a  push    rsi
0x18008884b  push    rdi
0x18008884c  push    r12
0x18008884e  push    r13
0x180088850  push    r14
0x180088852  push    r15
0x180088854  mov     rbp, rsp
0x180088857  sub     rsp, 40h
0x18008885b  xor     r12d, r12d
0x18008885e  lea     r9, [rbp+bufferLength]; bufferLength
0x180088862  mov     [rdx], r12
0x180088865  mov     r15, rdx
0x180088868  lea     rdx, [rbp+count]; count
0x18008886c  mov     [rbp+count], r12d
0x180088870  xor     r8d, r8d; packageFullNames
0x180088873  mov     [rbp+bufferLength], r12d
0x180088877  mov     r14, rcx
0x18008887a  mov     [rsp+40h+buffer], r12; buffer
0x18008887f  call    cs:__imp_GetPackagesByPackageFamily
0x180088885  test    eax, eax
0x180088887  jle     short loc_180088893
0x180088889  movzx   eax, ax
0x18008888c  or      eax, 80070000h
0x180088891  test    eax, eax
0x180088893  jns     loc_18008896E
0x180088899  cmp     eax, 8007007Ah
0x18008889e  jnz     loc_180088995
0x1800888a4  mov     r8d, [rbp+bufferLength]
0x1800888a8  lea     r9, [rbp+arg_18]
0x1800888ac  mov     r13d, 1
0x1800888b2  mov     [rbp+arg_18], r12
0x1800888b6  mov     edx, r13d
0x1800888b9  call    ??$_AllocArray@GVCTCoAllocPolicy@@@@YAJPEAXK_KPEAPEAG@Z; _AllocArray<ushort,CTCoAllocPolicy>(void *,ulong,unsigned __int64,ushort * *)
0x1800888be  mov     rdi, [rbp+arg_18]
0x1800888c2  mov     esi, eax
0x1800888c4  test    eax, eax
0x1800888c6  js      short loc_180088944
0x1800888c8  mov     rbx, r12
0x1800888cb  mov     [rbp+arg_18], rbx
0x1800888cf  cmp     [rbp+count], r13d
0x1800888d3  jnz     loc_180088967
0x1800888d9  lea     eax, [r13+7]
0x1800888dd  mul     r13
0x1800888e0  test    rdx, rdx
0x1800888e3  jz      loc_18008897B
0x1800888e9  mov     esi, 80070216h
0x1800888ee  test    esi, esi
0x1800888f0  js      short loc_18008893B
0x1800888f2  lea     r9, [rbp+bufferLength]; bufferLength
0x1800888f6  mov     [rsp+40h+buffer], rdi; buffer
0x1800888fb  mov     r8, rbx; packageFullNames
0x1800888fe  lea     rdx, [rbp+count]; count
0x180088902  mov     rcx, r14; packageFamilyName
0x180088905  call    cs:__imp_GetPackagesByPackageFamily
0x18008890b  mov     esi, eax
0x18008890d  test    eax, eax
0x18008890f  jle     short loc_18008891A
0x180088911  movzx   esi, ax
0x180088914  or      esi, 80070000h
0x18008891a  test    esi, esi
0x18008891c  js      short loc_18008893B
0x18008891e  mov     r8, [rbx]
0x180088921  or      r9, 0FFFFFFFFFFFFFFFFh
0x180088925  inc     r9
0x180088928  cmp     [r8+r9*2], r12w
0x18008892d  jnz     short loc_180088925
0x18008892f  mov     [rsp+40h+var_18], r15
0x180088934  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180088939  mov     esi, eax
0x18008893b  mov     rcx, rbx; pv
0x18008893e  call    cs:__imp_CoTaskMemFree
0x180088944  mov     rcx, rdi; pv
0x180088947  call    cs:__imp_CoTaskMemFree
0x18008894d  mov     rbx, [rsp+40h+arg_0]
0x180088955  mov     eax, esi
0x180088957  add     rsp, 40h
0x18008895b  pop     r15
0x18008895d  pop     r14
0x18008895f  pop     r13
0x180088961  pop     r12
0x180088963  pop     rdi
0x180088964  pop     rsi
0x180088965  pop     rbp
0x180088966  retn
0x180088967  mov     esi, 8000FFFFh
0x18008896c  jmp     short loc_18008893B
0x18008896e  cmp     [rbp+count], r12d
0x180088972  jnz     short loc_180088995
0x180088974  mov     esi, 80070490h
0x180088979  jmp     short loc_18008894D
0x18008897b  lea     r9, [rbp+arg_18]; void **
0x18008897f  mov     r8, rax; unsigned __int64
0x180088982  mov     edx, r13d; unsigned int
0x180088985  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18008898a  mov     rbx, [rbp+arg_18]
0x18008898e  mov     esi, eax
0x180088990  jmp     loc_1800888EE
0x180088995  mov     esi, 8000FFFFh
0x18008899a  jmp     short loc_18008894D
```
