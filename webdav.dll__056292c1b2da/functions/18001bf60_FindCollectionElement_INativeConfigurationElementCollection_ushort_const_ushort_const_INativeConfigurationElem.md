# FindCollectionElement(INativeConfigurationElementCollection *,ushort const *,ushort const *,INativeConfigurationElement * *)

- ea: `0x18001bf60`
- end: `0x18001c07d`
- name: `?FindCollectionElement@@YAJPEAVINativeConfigurationElementCollection@@PEBG1PEAPEAVINativeConfigurationElement@@@Z`
- size: `285`
- prototype: `int(struct INativeConfigurationElementCollection *, const unsigned __int16 *, const unsigned __int16 *, struct INativeConfigurationElement **)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180003a54`
- `0x180005184`

## callees

- `0x18001bf60`
- `0x180023010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001c008`
- `msvcrt!_wcsicmp` at `0x18001c008`

## pseudocode

```c
__int64 __fastcall FindCollectionElement(
        struct INativeConfigurationElementCollection *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct INativeConfigurationElement **a4)
{
  __int64 v4; // rax
  int v8; // ebx
  unsigned int v9; // edi
  struct INativeConfigurationElement *v10; // rax
  struct INativeConfigurationElement *v11; // rcx
  wchar_t *String1; // [rsp+30h] [rbp-10h] BYREF
  struct INativeConfigurationElement *v14; // [rsp+70h] [rbp+30h] BYREF
  const unsigned __int16 *v15; // [rsp+78h] [rbp+38h] BYREF

  v15 = a2;
  v4 = *(_QWORD *)a1;
  v14 = 0;
  LODWORD(v15) = 0;
  String1 = 0;
  v8 = (*(__int64 (__fastcall **)(struct INativeConfigurationElementCollection *, const unsigned __int16 **))(v4 + 24))(
         a1,
         &v15);
  if ( v8 < 0 )
  {
    v11 = v14;
  }
  else
  {
    v9 = 0;
    if ( (_DWORD)v15 )
    {
      while ( 1 )
      {
        v8 = (*(__int64 (__fastcall **)(struct INativeConfigurationElementCollection *, _QWORD, struct INativeConfigurationElement **))(*(_QWORD *)a1 + 32LL))(
               a1,
               v9,
               &v14);
        if ( v8 < 0 )
        {
          v10 = v14;
        }
        else
        {
          v8 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v14 + 64LL))(
                 v14,
                 L"name",
                 &String1,
                 0,
                 0);
          if ( v8 >= 0 && !_wcsicmp(String1, a3) )
            break;
          (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v14 + 16LL))(v14);
          v10 = 0;
          v14 = 0;
        }
        if ( ++v9 >= (unsigned int)v15 )
          goto LABEL_11;
      }
    }
    v10 = v14;
LABEL_11:
    if ( !v10 )
      return (unsigned int)-2147023728;
    v11 = 0;
    *a4 = v10;
    v14 = 0;
  }
  if ( v11 )
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v11 + 16LL))(v11);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001bf60  mov     [rsp-28h+arg_10], rbx
0x18001bf65  mov     [rsp-28h+arg_8], rdx
0x18001bf6a  push    rbp
0x18001bf6b  push    rsi
0x18001bf6c  push    rdi
0x18001bf6d  push    r14
0x18001bf6f  push    r15
0x18001bf71  mov     rbp, rsp
0x18001bf74  sub     rsp, 40h
0x18001bf78  mov     rax, [rcx]
0x18001bf7b  lea     rdx, [rbp+arg_8]
0x18001bf7f  mov     r14, r9
0x18001bf82  mov     [rbp+arg_0], 0
0x18001bf8a  mov     r15, r8
0x18001bf8d  mov     dword ptr [rbp+arg_8], 0
0x18001bf94  mov     rsi, rcx
0x18001bf97  mov     [rbp+String1], 0
0x18001bf9f  mov     rax, [rax+18h]
0x18001bfa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bfa8  mov     ebx, eax
0x18001bfaa  test    eax, eax
0x18001bfac  js      loc_18001C052
0x18001bfb2  xor     edi, edi
0x18001bfb4  cmp     dword ptr [rbp+arg_8], edi
0x18001bfb7  jbe     short loc_18001C037
0x18001bfb9  mov     rax, [rsi]
0x18001bfbc  lea     r8, [rbp+arg_0]
0x18001bfc0  mov     edx, edi
0x18001bfc2  mov     rcx, rsi
0x18001bfc5  mov     rax, [rax+20h]
0x18001bfc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bfce  mov     ebx, eax
0x18001bfd0  test    eax, eax
0x18001bfd2  js      short loc_18001C02A
0x18001bfd4  mov     rcx, [rbp+arg_0]
0x18001bfd8  lea     r8, [rbp+String1]
0x18001bfdc  xor     r9d, r9d
0x18001bfdf  mov     [rsp+40h+var_20], 0
0x18001bfe8  lea     rdx, aName; "name"
0x18001bfef  mov     rax, [rcx]
0x18001bff2  mov     rax, [rax+40h]
0x18001bff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bffb  mov     ebx, eax
0x18001bffd  test    eax, eax
0x18001bfff  js      short loc_18001C012
0x18001c001  mov     rcx, [rbp+String1]; String1
0x18001c005  mov     rdx, r15; String2
0x18001c008  call    cs:__imp__wcsicmp
0x18001c00e  test    eax, eax
0x18001c010  jz      short loc_18001C037
0x18001c012  mov     rcx, [rbp+arg_0]
0x18001c016  mov     rax, [rcx]
0x18001c019  mov     rax, [rax+10h]
0x18001c01d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c022  xor     eax, eax
0x18001c024  mov     [rbp+arg_0], rax
0x18001c028  jmp     short loc_18001C02E
0x18001c02a  mov     rax, [rbp+arg_0]
0x18001c02e  inc     edi
0x18001c030  cmp     edi, dword ptr [rbp+arg_8]
0x18001c033  jb      short loc_18001BFB9
0x18001c035  jmp     short loc_18001C03B
0x18001c037  mov     rax, [rbp+arg_0]
0x18001c03b  test    rax, rax
0x18001c03e  jnz     short loc_18001C047
0x18001c040  mov     ebx, 80070490h
0x18001c045  jmp     short loc_18001C067
0x18001c047  xor     ecx, ecx
0x18001c049  mov     [r14], rax
0x18001c04c  mov     [rbp+arg_0], rcx
0x18001c050  jmp     short loc_18001C056
0x18001c052  mov     rcx, [rbp+arg_0]
0x18001c056  test    rcx, rcx
0x18001c059  jz      short loc_18001C067
0x18001c05b  mov     rax, [rcx]
0x18001c05e  mov     rax, [rax+10h]
0x18001c062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c067  mov     eax, ebx
0x18001c069  mov     rbx, [rsp+40h+arg_10]
0x18001c071  add     rsp, 40h
0x18001c075  pop     r15
0x18001c077  pop     r14
0x18001c079  pop     rdi
0x18001c07a  pop     rsi
0x18001c07b  pop     rbp
0x18001c07c  retn
```
