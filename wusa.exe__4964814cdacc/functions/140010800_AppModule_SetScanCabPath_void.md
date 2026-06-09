# AppModule::SetScanCabPath(void)

- ea: `0x140010800`
- end: `0x1400108d4`
- name: `?SetScanCabPath@AppModule@@AEAAJXZ`
- size: `212`
- prototype: `__int64 __fastcall(AppModule *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000f8f0`

## callees

- `0x140001a63`
- `0x1400044e0`
- `0x140010800`
- `0x140013490`
- `0x140014910`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140010882`
- `OLEAUT32!__imp_SysAllocString` at `0x140010882`

## string_xrefs

- `0x140010863`: `Failed to build the full path for offline scan cab`
- `0x14001086f`: `AppModule::SetScanCabPath`
- `0x1400108a0`: `AppModule::SetScanCabPath`
- `0x140010894`: `Failed to allocate memory for scan cab path`

## pseudocode

```c
__int64 __fastcall AppModule::SetScanCabPath(AppModule *this)
{
  int v2; // ebx
  BSTR v3; // rax
  OLECHAR psz[264]; // [rsp+30h] [rbp-228h] BYREF

  memset_0(psz, 0, 0x208u);
  v2 = StringCchPrintfW(psz, 0x104u, L"%s\\%s", *((_QWORD *)this + 22), L"wsusscan.cab");
  if ( v2 >= 0 )
  {
    v3 = SysAllocString(psz);
    *((_QWORD *)this + 19) = v3;
    if ( !v3 )
    {
      WusaLogDebugEventA(L"AppModule::SetScanCabPath", 830, "Failed to allocate memory for scan cab path");
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    WusaLogDebugEventA(L"AppModule::SetScanCabPath", 827, "Failed to build the full path for offline scan cab");
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140010800  mov     [rsp+arg_8], rbx
0x140010805  push    rdi
0x140010806  sub     rsp, 250h
0x14001080d  mov     rax, cs:__security_cookie
0x140010814  xor     rax, rsp
0x140010817  mov     [rsp+258h+var_18], rax
0x14001081f  mov     rdi, rcx
0x140010822  xor     edx, edx; Val
0x140010824  lea     rcx, [rsp+258h+psz]; void *
0x140010829  mov     r8d, 208h; Size
0x14001082f  call    memset_0
0x140010834  mov     r9, [rdi+0B0h]
0x14001083b  lea     rax, aWsusscanCab_0; "wsusscan.cab"
0x140010842  lea     r8, aSS; "%s\\%s"
0x140010849  mov     [rsp+258h+var_238], rax
0x14001084e  mov     edx, 104h; unsigned __int64
0x140010853  lea     rcx, [rsp+258h+psz]; unsigned __int16 *
0x140010858  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14001085d  mov     ebx, eax
0x14001085f  test    eax, eax
0x140010861  jns     short loc_14001087D
0x140010863  lea     r8, aFailedToBuildT; "Failed to build the full path for offli"...
0x14001086a  mov     edx, 33Bh
0x14001086f  lea     rcx, aAppmoduleSetsc; "AppModule::SetScanCabPath"
0x140010876  call    WusaLogDebugEventA
0x14001087b  jmp     short loc_1400108B1
0x14001087d  lea     rcx, [rsp+258h+psz]; psz
0x140010882  call    cs:__imp_SysAllocString
0x140010888  mov     [rdi+98h], rax
0x14001088f  test    rax, rax
0x140010892  jnz     short loc_1400108B1
0x140010894  lea     r8, aFailedToAlloca_25; "Failed to allocate memory for scan cab "...
0x14001089b  mov     edx, 33Eh
0x1400108a0  lea     rcx, aAppmoduleSetsc; "AppModule::SetScanCabPath"
0x1400108a7  call    WusaLogDebugEventA
0x1400108ac  mov     ebx, 8007000Eh
0x1400108b1  mov     eax, ebx
0x1400108b3  mov     rcx, [rsp+258h+var_18]
0x1400108bb  xor     rcx, rsp; StackCookie
0x1400108be  call    __security_check_cookie
0x1400108c3  mov     rbx, [rsp+258h+arg_8]
0x1400108cb  add     rsp, 250h
0x1400108d2  pop     rdi
0x1400108d3  retn
```
