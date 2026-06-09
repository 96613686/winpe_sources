# CallerIdentity::GetPackageFamilyNameFromProcess(void *,ushort * *)

- ea: `0x18001a320`
- end: `0x18001a3e4`
- name: `?GetPackageFamilyNameFromProcess@CallerIdentity@@YAJPEAXPEAPEAG@Z`
- size: `196`
- prototype: `__int64 __fastcall(HANDLE hProcess, PWSTR *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001a0e8`

## callees

- `0x18001a320`
- `0x18001a3ec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a378`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a3cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a378`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a3cf`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFamilyName` at `0x18001a349`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFamilyName` at `0x18001a3ab`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFamilyName` at `0x18001a349`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFamilyName` at `0x18001a3ab`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetPackageFamilyNameFromProcess(HANDLE hProcess, PWSTR *a2, unsigned __int16 **a3)
{
  LONG v5; // eax
  signed int v6; // edi
  int v7; // edx
  int v8; // ecx
  int v9; // eax
  PWSTR v10; // rbx
  LONG v11; // eax
  PWSTR v12; // rax
  UINT32 packageFamilyNameLength; // [rsp+58h] [rbp+10h] BYREF
  PWSTR packageFamilyName; // [rsp+60h] [rbp+18h]

  *a2 = 0;
  packageFamilyNameLength = 0;
  v5 = GetPackageFamilyName(hProcess, &packageFamilyNameLength, 0);
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  if ( v6 == -2147024774 && packageFamilyNameLength )
  {
    packageFamilyName = 0;
    CoTaskMemFree(0);
    v9 = _AllocStringWorker<CTCoAllocPolicy>(v8, v7, 0, packageFamilyNameLength);
    v10 = packageFamilyName;
    v6 = v9;
    if ( v9 >= 0 )
    {
      v11 = GetPackageFamilyName(hProcess, &packageFamilyNameLength, packageFamilyName);
      v6 = v11;
      if ( v11 > 0 )
        v6 = (unsigned __int16)v11 | 0x80070000;
      if ( v6 >= 0 )
      {
        v12 = v10;
        v10 = 0;
        *a2 = v12;
      }
    }
    CoTaskMemFree(v10);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001a320  mov     [rsp+arg_0], rbx
0x18001a325  push    rbp
0x18001a326  push    rsi
0x18001a327  push    rdi
0x18001a328  sub     rsp, 30h
0x18001a32c  mov     rsi, rdx
0x18001a32f  mov     qword ptr [rdx], 0
0x18001a336  lea     rdx, [rsp+48h+packageFamilyNameLength]; packageFamilyNameLength
0x18001a33b  mov     [rsp+48h+packageFamilyNameLength], 0
0x18001a343  xor     r8d, r8d; packageFamilyName
0x18001a346  mov     rbp, rcx
0x18001a349  call    cs:__imp_GetPackageFamilyName
0x18001a34f  mov     edi, eax
0x18001a351  test    eax, eax
0x18001a353  jle     short loc_18001A35E
0x18001a355  movzx   edi, ax
0x18001a358  or      edi, 80070000h
0x18001a35e  cmp     edi, 8007007Ah
0x18001a364  jnz     short loc_18001A3D5
0x18001a366  cmp     [rsp+48h+packageFamilyNameLength], 0
0x18001a36b  jbe     short loc_18001A3D5
0x18001a36d  xor     ecx, ecx; pv
0x18001a36f  mov     [rsp+48h+packageFamilyName], 0
0x18001a378  call    cs:__imp_CoTaskMemFree
0x18001a37e  mov     r9d, [rsp+48h+packageFamilyNameLength]
0x18001a383  lea     rax, [rsp+48h+packageFamilyName]
0x18001a388  xor     r8d, r8d
0x18001a38b  mov     [rsp+48h+var_20], rax
0x18001a390  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18001a395  mov     rbx, [rsp+48h+packageFamilyName]
0x18001a39a  mov     edi, eax
0x18001a39c  test    eax, eax
0x18001a39e  js      short loc_18001A3CC
0x18001a3a0  mov     r8, rbx; packageFamilyName
0x18001a3a3  lea     rdx, [rsp+48h+packageFamilyNameLength]; packageFamilyNameLength
0x18001a3a8  mov     rcx, rbp; hProcess
0x18001a3ab  call    cs:__imp_GetPackageFamilyName
0x18001a3b1  mov     edi, eax
0x18001a3b3  test    eax, eax
0x18001a3b5  jle     short loc_18001A3C0
0x18001a3b7  movzx   edi, ax
0x18001a3ba  or      edi, 80070000h
0x18001a3c0  test    edi, edi
0x18001a3c2  js      short loc_18001A3CC
0x18001a3c4  mov     rax, rbx
0x18001a3c7  xor     ebx, ebx
0x18001a3c9  mov     [rsi], rax
0x18001a3cc  mov     rcx, rbx; pv
0x18001a3cf  call    cs:__imp_CoTaskMemFree
0x18001a3d5  mov     rbx, [rsp+48h+arg_0]
0x18001a3da  mov     eax, edi
0x18001a3dc  add     rsp, 30h
0x18001a3e0  pop     rdi
0x18001a3e1  pop     rsi
0x18001a3e2  pop     rbp
0x18001a3e3  retn
```
