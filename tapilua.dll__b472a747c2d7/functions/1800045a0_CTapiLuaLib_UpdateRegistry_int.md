# CTapiLuaLib::UpdateRegistry(int)

- ea: `0x1800045a0`
- end: `0x180004729`
- name: `?UpdateRegistry@CTapiLuaLib@@SAJH@Z`
- size: `393`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callees

- `0x180001470`
- `0x180001d0e`
- `0x180001f38`
- `0x18000200c`
- `0x180003688`
- `0x1800045a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800045e6`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800045e6`
- `KERNEL32!GetLastError` at `0x18000463e`
- `KERNEL32!GetLastError` at `0x18000463e`
- `KERNEL32!GetModuleFileNameW` at `0x18000461b`
- `KERNEL32!GetModuleFileNameW` at `0x18000461b`

## string_xrefs

- `0x1800046cb`: `REGISTRY`
- `0x1800046e9`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall CTapiLuaLib::UpdateRegistry(int a1)
{
  DWORD ModuleFileNameW; // eax
  int v3; // ebx
  signed int LastError; // eax
  unsigned __int16 *v5; // rcx
  WCHAR v6; // ax
  WCHAR *v7; // rdx
  const unsigned __int16 *v8; // r8
  void *v10; // [rsp+30h] [rbp-D0h] BYREF
  int v11; // [rsp+38h] [rbp-C8h]
  int v12; // [rsp+3Ch] [rbp-C4h]
  __int64 v13; // [rsp+48h] [rbp-B8h]
  __int64 v14; // [rsp+50h] [rbp-B0h]
  __int64 v15; // [rsp+58h] [rbp-A8h]
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v17[528]; // [rsp+270h] [rbp+170h] BYREF

  v14 = -2;
  v15 = 0;
  v11 = 0;
  v12 = 10;
  v10 = malloc(0x50u);
  memset_0(Filename, 0, 0x20Au);
  ModuleFileNameW = GetModuleFileNameW(*((HMODULE *)ATL::_pModule + 1), Filename, 0x104u);
  if ( ModuleFileNameW == 260 )
  {
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v10);
    return (unsigned int)-2147024785;
  }
  else
  {
    if ( ModuleFileNameW )
    {
      v5 = v17;
      v6 = Filename[0];
      if ( Filename[0] )
      {
        v7 = Filename;
        do
        {
          *v5++ = v6;
          if ( v6 == 39 )
            *v5++ = 39;
          v6 = *++v7;
        }
        while ( *v7 );
      }
      *v5 = 0;
      v3 = ATL::CRegObject::AddReplacement((ATL::CRegObject *)&v10, L"Module", v17);
      if ( v3 >= 0 )
      {
        v13 = 0;
        if ( a1 )
          v3 = ATL::CRegObject::RegisterFromResource((const WCHAR *)&v10, Filename, v8, L"REGISTRY", 1);
        else
          v3 = ATL::CRegObject::RegisterFromResource((const WCHAR *)&v10, Filename, v8, L"REGISTRY", 0);
      }
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v10);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800045a0  push    rbp
0x1800045a2  push    rbx
0x1800045a3  push    rsi
0x1800045a4  push    rdi
0x1800045a5  lea     rbp, [rsp-5A8h]
0x1800045ad  sub     rsp, 6A8h
0x1800045b4  mov     [rsp+6C0h+var_670], 0FFFFFFFFFFFFFFFEh
0x1800045bd  mov     rax, cs:__security_cookie
0x1800045c4  xor     rax, rsp
0x1800045c7  mov     [rbp+5C0h+var_30], rax
0x1800045ce  mov     edi, ecx
0x1800045d0  xor     esi, esi
0x1800045d2  mov     [rsp+6C0h+var_668], rsi
0x1800045d7  mov     [rsp+6C0h+var_688], esi
0x1800045db  mov     [rsp+6C0h+var_684], 0Ah
0x1800045e3  lea     ecx, [rsi+50h]; Size
0x1800045e6  call    cs:__imp_malloc
0x1800045ec  mov     [rsp+6C0h+var_690], rax
0x1800045f1  xor     edx, edx; Val
0x1800045f3  mov     r8d, 20Ah; Size
0x1800045f9  lea     rcx, [rsp+6C0h+Filename]; void *
0x1800045fe  call    memset_0
0x180004603  mov     ebx, 104h
0x180004608  mov     r8d, ebx; nSize
0x18000460b  lea     rdx, [rsp+6C0h+Filename]; lpFilename
0x180004610  mov     rcx, cs:?_pModule@ATL@@3PEAVCComModule@1@EA; ATL::CComModule * ATL::_pModule
0x180004617  mov     rcx, [rcx+8]; hModule
0x18000461b  call    cs:__imp_GetModuleFileNameW
0x180004621  cmp     eax, ebx
0x180004623  jnz     short loc_18000463A
0x180004625  lea     rcx, [rsp+6C0h+var_690]; this
0x18000462a  call    ??1CRegObject@ATL@@QEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000462f  nop
0x180004630  mov     ebx, 8007006Fh
0x180004635  jmp     loc_18000470C
0x18000463a  test    eax, eax
0x18000463c  jnz     short loc_18000465C
0x18000463e  call    cs:__imp_GetLastError
0x180004644  mov     ebx, eax
0x180004646  test    eax, eax
0x180004648  jle     loc_180004701
0x18000464e  movzx   ebx, ax
0x180004651  or      ebx, 80070000h
0x180004657  jmp     loc_180004701
0x18000465c  lea     rcx, [rbp+5C0h+var_450]
0x180004663  movzx   eax, [rsp+6C0h+Filename]
0x180004668  test    ax, ax
0x18000466b  jz      short loc_180004699
0x18000466d  lea     rdx, [rsp+6C0h+Filename]
0x180004672  mov     r8d, 27h ; '''
0x180004678  mov     [rcx], ax
0x18000467b  add     rcx, 2
0x18000467f  cmp     ax, r8w
0x180004683  jnz     short loc_18000468D
0x180004685  mov     [rcx], r8w
0x180004689  add     rcx, 2
0x18000468d  add     rdx, 2
0x180004691  movzx   eax, word ptr [rdx]
0x180004694  test    ax, ax
0x180004697  jnz     short loc_180004678
0x180004699  mov     [rcx], si
0x18000469c  lea     r8, [rbp+5C0h+var_450]; unsigned __int16 *
0x1800046a3  lea     rdx, String2; "Module"
0x1800046aa  lea     rcx, [rsp+6C0h+var_690]; this
0x1800046af  call    ?AddReplacement@CRegObject@ATL@@QEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x1800046b4  mov     ebx, eax
0x1800046b6  test    eax, eax
0x1800046b8  js      short loc_180004701
0x1800046ba  mov     [rsp+6C0h+var_678], rsi
0x1800046bf  test    edi, edi
0x1800046c1  jz      short loc_1800046E5
0x1800046c3  mov     [rsp+6C0h+var_6A0], 1; int
0x1800046cb  lea     r9, aRegistry; "REGISTRY"
0x1800046d2  lea     rdx, [rsp+6C0h+Filename]; unsigned __int16 *
0x1800046d7  lea     rcx, [rsp+6C0h+var_690]; this
0x1800046dc  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x1800046e1  mov     ebx, eax
0x1800046e3  jmp     short loc_180004701
0x1800046e5  mov     [rsp+6C0h+var_6A0], esi; int
0x1800046e9  lea     r9, aRegistry; "REGISTRY"
0x1800046f0  lea     rdx, [rsp+6C0h+Filename]; unsigned __int16 *
0x1800046f5  lea     rcx, [rsp+6C0h+var_690]; this
0x1800046fa  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x1800046ff  mov     ebx, eax
0x180004701  lea     rcx, [rsp+6C0h+var_690]; this
0x180004706  call    ??1CRegObject@ATL@@QEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000470b  nop
0x18000470c  mov     eax, ebx
0x18000470e  mov     rcx, [rbp+5C0h+var_30]
0x180004715  xor     rcx, rsp; StackCookie
0x180004718  call    __security_check_cookie
0x18000471d  add     rsp, 6A8h
0x180004724  pop     rdi
0x180004725  pop     rsi
0x180004726  pop     rbx
0x180004727  pop     rbp
0x180004728  retn
```
