# CbsClient::CreatePackage(ushort const *)

- ea: `0x140010e88`
- end: `0x140010fde`
- name: `?CreatePackage@CbsClient@@QEAAJPEBG@Z`
- size: `342`
- prototype: `__int64 __fastcall(CbsClient *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14000afc0`

## callees

- `0x14000e280`
- `0x140010e1c`
- `0x140010e88`
- `0x14001150c`
- `0x140013490`
- `0x140015010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140010fc6`
- `KERNEL32!LocalFree` at `0x140010fc6`

## string_xrefs

- `0x140010e9b`: `CbsClient::CreatePackage`
- `0x140010efe`: `Failed to create a CBS package`

## pseudocode

```c
__int64 __fastcall CbsClient::CreatePackage(CbsClient *this, const unsigned __int16 *a2, __int64 a3)
{
  bool v3; // zf
  signed int Properties; // ebx
  __int64 v7; // rdx
  __int64 v8; // r8
  HLOCAL v9; // rdi
  __int64 v11; // [rsp+50h] [rbp+8h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp+18h] BYREF

  v3 = *(_QWORD *)this == 0;
  v11 = 0;
  if ( v3 )
  {
    Properties = -2147418113;
    WusaLogDebugEventA(L"CbsClient::CreatePackage", 160, "CBS session is not initialized.");
  }
  else
  {
    CbsClient::ClosePackage(this, (__int64)a2, a3);
    Properties = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, const unsigned __int16 *, char *, __int64 *))(**(_QWORD **)this + 40LL))(
                   *(_QWORD *)this,
                   0,
                   0,
                   a2,
                   (char *)this + 16,
                   &v11);
    if ( Properties >= 0 )
    {
      Properties = (**(__int64 (__fastcall ***)(__int64, GUID *, char *))v11)(
                     v11,
                     &GUID_75207393_23f2_4396_85f0_8fdb879ed0ed,
                     (char *)this + 8);
      if ( Properties >= 0 )
      {
        Properties = CbsClient::QueryProperties(this);
        if ( Properties < 0 )
          WusaLogDebugEventA(L"CbsClient::CreatePackage", 172, "Failed to query properties");
      }
      else
      {
        WusaLogDebugEventA(L"CbsClient::CreatePackage", 169, "Failed to QI on a CBS package");
      }
    }
    else
    {
      WusaLogDebugEventA(L"CbsClient::CreatePackage", 166, "Failed to create a CBS package");
    }
  }
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v11 = 0;
  }
  if ( Properties < 0 )
  {
    CbsClient::ClosePackage(this, v7, v8);
    hMem = 0;
    WusaGetErrorMessage(Properties, (unsigned __int16 **)&hMem);
    v9 = hMem;
    WusaLogDebugEventA(
      L"CbsClient::CreatePackage",
      183,
      "Exit with error code 0X%x (%ls)",
      Properties,
      (const wchar_t *)hMem);
    if ( v9 )
      LocalFree(v9);
  }
  return (unsigned int)Properties;
}

```

## disassembly

```asm
0x140010e88  mov     [rsp+arg_8], rbx
0x140010e8d  mov     [rsp+arg_18], rbp
0x140010e92  push    rdi
0x140010e93  sub     rsp, 40h
0x140010e97  cmp     qword ptr [rcx], 0
0x140010e9b  lea     rbp, aCbsclientCreat; "CbsClient::CreatePackage"
0x140010ea2  mov     rbx, rdx
0x140010ea5  mov     [rsp+48h+arg_0], 0
0x140010eae  mov     rdi, rcx
0x140010eb1  jnz     short loc_140010EC9
0x140010eb3  mov     ebx, 8000FFFFh
0x140010eb8  lea     r8, aCbsSessionIsNo; "CBS session is not initialized."
0x140010ebf  mov     edx, 0A0h
0x140010ec4  jmp     loc_140010F55
0x140010ec9  call    ?ClosePackage@CbsClient@@AEAAXXZ; CbsClient::ClosePackage(void)
0x140010ece  mov     rcx, [rdi]
0x140010ed1  lea     r8, [rsp+48h+arg_0]
0x140010ed6  lea     rdx, [rdi+10h]
0x140010eda  mov     [rsp+48h+var_20], r8
0x140010edf  mov     [rsp+48h+var_28], rdx
0x140010ee4  mov     r9, rbx
0x140010ee7  xor     r8d, r8d
0x140010eea  xor     edx, edx
0x140010eec  mov     rax, [rcx]
0x140010eef  mov     rax, [rax+28h]
0x140010ef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010ef8  mov     ebx, eax
0x140010efa  test    eax, eax
0x140010efc  jns     short loc_140010F0C
0x140010efe  lea     r8, aFailedToCreate_3; "Failed to create a CBS package"
0x140010f05  mov     edx, 0A6h
0x140010f0a  jmp     short loc_140010F55
0x140010f0c  mov     rcx, [rsp+48h+arg_0]
0x140010f11  lea     r8, [rdi+8]
0x140010f15  lea     rdx, _GUID_75207393_23f2_4396_85f0_8fdb879ed0ed
0x140010f1c  mov     rax, [rcx]
0x140010f1f  mov     rax, [rax]
0x140010f22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010f27  mov     ebx, eax
0x140010f29  test    eax, eax
0x140010f2b  jns     short loc_140010F3B
0x140010f2d  lea     r8, aFailedToQiOnAC; "Failed to QI on a CBS package"
0x140010f34  mov     edx, 0A9h
0x140010f39  jmp     short loc_140010F55
0x140010f3b  mov     rcx, rdi; this
0x140010f3e  call    ?QueryProperties@CbsClient@@AEAAJXZ; CbsClient::QueryProperties(void)
0x140010f43  mov     ebx, eax
0x140010f45  test    eax, eax
0x140010f47  jns     short loc_140010F5D
0x140010f49  lea     r8, aFailedToQueryP; "Failed to query properties"
0x140010f50  mov     edx, 0ACh
0x140010f55  mov     rcx, rbp
0x140010f58  call    WusaLogDebugEventA
0x140010f5d  mov     rcx, [rsp+48h+arg_0]
0x140010f62  test    rcx, rcx
0x140010f65  jz      short loc_140010F7C
0x140010f67  mov     rax, [rcx]
0x140010f6a  mov     rax, [rax+10h]
0x140010f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010f73  mov     [rsp+48h+arg_0], 0
0x140010f7c  test    ebx, ebx
0x140010f7e  jns     short loc_140010FCC
0x140010f80  mov     rcx, rdi; this
0x140010f83  call    ?ClosePackage@CbsClient@@AEAAXXZ; CbsClient::ClosePackage(void)
0x140010f88  lea     rdx, [rsp+48h+hMem]; unsigned __int16 **
0x140010f8d  mov     [rsp+48h+hMem], 0
0x140010f96  mov     ecx, ebx; dwMessageId
0x140010f98  call    ?WusaGetErrorMessage@@YAJKPEAPEAG@Z; WusaGetErrorMessage(ulong,ushort * *)
0x140010f9d  mov     rdi, [rsp+48h+hMem]
0x140010fa2  lea     r8, aExitWithErrorC; "Exit with error code 0X%x (%ls)"
0x140010fa9  mov     r9d, ebx
0x140010fac  mov     [rsp+48h+var_28], rdi
0x140010fb1  mov     edx, 0B7h
0x140010fb6  mov     rcx, rbp
0x140010fb9  call    WusaLogDebugEventA
0x140010fbe  test    rdi, rdi
0x140010fc1  jz      short loc_140010FCC
0x140010fc3  mov     rcx, rdi; hMem
0x140010fc6  call    cs:__imp_LocalFree
0x140010fcc  mov     rbp, [rsp+48h+arg_18]
0x140010fd1  mov     eax, ebx
0x140010fd3  mov     rbx, [rsp+48h+arg_8]
0x140010fd8  add     rsp, 40h
0x140010fdc  pop     rdi
0x140010fdd  retn
```
