# ATL::CComModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x14000c860`
- end: `0x14000c9b3`
- name: `?UpdateRegistryFromResourceS@CComModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `339`
- prototype: `__int64 __fastcall(ATL::CComModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14000c850`
- `0x14000ccb8`

## callees

- `0x140001390`
- `0x140001d26`
- `0x140009c24`
- `0x140009d70`
- `0x14000b9a0`
- `0x14000c860`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x14000c8ce`
- `KERNEL32!GetModuleFileNameW` at `0x14000c8ce`
- `KERNEL32!GetLastError` at `0x14000c8e6`
- `KERNEL32!GetLastError` at `0x14000c8e6`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14000c899`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14000c899`

## string_xrefs

- `0x14000c962`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CComModule::UpdateRegistryFromResourceS(
        ATL::CComModule *this,
        __int64 a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  DWORD ModuleFileNameW; // eax
  int v6; // ebx
  signed int LastError; // eax
  WCHAR v8; // ax
  unsigned __int16 *v9; // rcx
  WCHAR *v10; // rdx
  const unsigned __int16 *v11; // r8
  int v12; // eax
  void *v14; // [rsp+30h] [rbp-D0h] BYREF
  int v15; // [rsp+38h] [rbp-C8h]
  int v16; // [rsp+3Ch] [rbp-C4h]
  WCHAR Filename[264]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v18[528]; // [rsp+260h] [rbp+160h] BYREF

  v16 = 10;
  v15 = 0;
  v14 = malloc(0x50u);
  memset_0(Filename, 0, 0x20Au);
  ModuleFileNameW = GetModuleFileNameW(*((HMODULE *)ATL::_pModule + 1), Filename, 0x104u);
  if ( ModuleFileNameW == 260 )
  {
    v6 = -2147024785;
  }
  else if ( ModuleFileNameW )
  {
    v8 = Filename[0];
    v9 = v18;
    if ( Filename[0] )
    {
      v10 = Filename;
      do
      {
        *v9++ = v8;
        if ( v8 == 39 )
          *v9++ = 39;
        v8 = *++v10;
      }
      while ( *v10 );
    }
    *v9 = 0;
    v6 = ATL::CRegObject::AddReplacement((ATL::CRegObject *)&v14, L"Module", v18);
    if ( v6 >= 0 )
    {
      if ( a3 )
        v12 = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v14, Filename, v11, L"REGISTRY", 1);
      else
        v12 = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v14, Filename, v11, L"REGISTRY", 0);
      v6 = v12;
    }
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
  }
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v14);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14000c860  push    rbp
0x14000c862  push    rbx
0x14000c863  push    rsi
0x14000c864  push    rdi
0x14000c865  lea     rbp, [rsp-598h]
0x14000c86d  sub     rsp, 698h
0x14000c874  mov     rax, cs:__security_cookie
0x14000c87b  xor     rax, rsp
0x14000c87e  mov     [rbp+5B0h+var_30], rax
0x14000c885  xor     esi, esi
0x14000c887  mov     [rsp+6B0h+var_674], 0Ah
0x14000c88f  mov     edi, r8d
0x14000c892  mov     [rsp+6B0h+var_678], esi
0x14000c896  lea     ecx, [rsi+50h]; Size
0x14000c899  call    cs:__imp_malloc
0x14000c89f  xor     edx, edx; Val
0x14000c8a1  lea     rcx, [rsp+6B0h+Filename]; void *
0x14000c8a6  mov     r8d, 20Ah; Size
0x14000c8ac  mov     [rsp+6B0h+var_680], rax
0x14000c8b1  call    memset_0
0x14000c8b6  mov     rcx, cs:?_pModule@ATL@@3PEAVCComModule@1@EA; ATL::CComModule * ATL::_pModule
0x14000c8bd  lea     rdx, [rsp+6B0h+Filename]; lpFilename
0x14000c8c2  mov     ebx, 104h
0x14000c8c7  mov     r8d, ebx; nSize
0x14000c8ca  mov     rcx, [rcx+8]; hModule
0x14000c8ce  call    cs:__imp_GetModuleFileNameW
0x14000c8d4  cmp     eax, ebx
0x14000c8d6  jnz     short loc_14000C8E2
0x14000c8d8  mov     ebx, 8007006Fh
0x14000c8dd  jmp     loc_14000C98C
0x14000c8e2  test    eax, eax
0x14000c8e4  jnz     short loc_14000C904
0x14000c8e6  call    cs:__imp_GetLastError
0x14000c8ec  mov     ebx, eax
0x14000c8ee  test    eax, eax
0x14000c8f0  jle     loc_14000C98C
0x14000c8f6  movzx   ebx, ax
0x14000c8f9  or      ebx, 80070000h
0x14000c8ff  jmp     loc_14000C98C
0x14000c904  movzx   eax, [rsp+6B0h+Filename]
0x14000c909  lea     rcx, [rbp+5B0h+var_450]
0x14000c910  test    ax, ax
0x14000c913  jz      short loc_14000C941
0x14000c915  lea     rdx, [rsp+6B0h+Filename]
0x14000c91a  mov     r8d, 27h ; '''
0x14000c920  mov     [rcx], ax
0x14000c923  add     rcx, 2
0x14000c927  cmp     ax, r8w
0x14000c92b  jnz     short loc_14000C935
0x14000c92d  mov     [rcx], r8w
0x14000c931  add     rcx, 2
0x14000c935  add     rdx, 2
0x14000c939  movzx   eax, word ptr [rdx]
0x14000c93c  test    ax, ax
0x14000c93f  jnz     short loc_14000C920
0x14000c941  mov     [rcx], si
0x14000c944  lea     r8, [rbp+5B0h+var_450]; unsigned __int16 *
0x14000c94b  lea     rcx, [rsp+6B0h+var_680]; this
0x14000c950  lea     rdx, aModule; "Module"
0x14000c957  call    ?AddReplacement@CRegObject@ATL@@QEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x14000c95c  mov     ebx, eax
0x14000c95e  test    eax, eax
0x14000c960  js      short loc_14000C98C
0x14000c962  lea     r9, aRegistry; "REGISTRY"
0x14000c969  lea     rdx, [rsp+6B0h+Filename]; unsigned __int16 *
0x14000c96e  lea     rcx, [rsp+6B0h+var_680]; this
0x14000c973  test    edi, edi
0x14000c975  jz      short loc_14000C981
0x14000c977  mov     [rsp+6B0h+var_690], 1
0x14000c97f  jmp     short loc_14000C985
0x14000c981  mov     [rsp+6B0h+var_690], esi; int
0x14000c985  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x14000c98a  mov     ebx, eax
0x14000c98c  lea     rcx, [rsp+6B0h+var_680]; this
0x14000c991  call    ??1CRegObject@ATL@@QEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x14000c996  mov     eax, ebx
0x14000c998  mov     rcx, [rbp+5B0h+var_30]
0x14000c99f  xor     rcx, rsp; StackCookie
0x14000c9a2  call    __security_check_cookie
0x14000c9a7  add     rsp, 698h
0x14000c9ae  pop     rdi
0x14000c9af  pop     rsi
0x14000c9b0  pop     rbx
0x14000c9b1  pop     rbp
0x14000c9b2  retn
```
