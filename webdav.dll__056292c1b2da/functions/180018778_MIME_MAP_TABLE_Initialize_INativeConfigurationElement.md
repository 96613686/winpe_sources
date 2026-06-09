# MIME_MAP_TABLE::Initialize(INativeConfigurationElement *)

- ea: `0x180018778`
- end: `0x180018902`
- name: `?Initialize@MIME_MAP_TABLE@@QEAAJPEAVINativeConfigurationElement@@@Z`
- size: `394`
- prototype: `__int64 __fastcall(MIME_MAP_TABLE *__hidden this, struct INativeConfigurationElement *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001863c`

## callees

- `0x180018558`
- `0x180018778`
- `0x180023010`

## string_xrefs

- `0x18001882e`: `fileExtension`

## pseudocode

```c
__int64 __fastcall MIME_MAP_TABLE::Initialize(MIME_MAP_TABLE *this, struct INativeConfigurationElement *a2)
{
  __int64 v2; // rax
  __int64 (__fastcall *v4)(struct INativeConfigurationElement *, __int64 *); // rax
  int v5; // ebx
  unsigned int v6; // edi
  unsigned __int16 *v8; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int16 *v9; // [rsp+38h] [rbp-8h] BYREF
  unsigned int v10; // [rsp+68h] [rbp+28h] BYREF
  __int64 v11; // [rsp+70h] [rbp+30h] BYREF
  __int64 v12; // [rsp+78h] [rbp+38h] BYREF

  v2 = *(_QWORD *)a2;
  v12 = 0;
  v11 = 0;
  v10 = 0;
  v4 = *(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(v2 + 40);
  v8 = 0;
  v9 = 0;
  v5 = v4(a2, &v12);
  if ( v5 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v12 + 24LL))(v12, &v10);
    if ( v5 >= 0 )
    {
      v6 = 0;
      if ( !v10 )
      {
LABEL_9:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        return 0;
      }
      while ( 1 )
      {
        v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v12 + 32LL))(v12, v6, &v11);
        if ( v5 < 0 )
          break;
        v5 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v11 + 64LL))(
               v11,
               L"fileExtension",
               &v8,
               0,
               0);
        if ( v5 < 0 )
          break;
        v5 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v11 + 64LL))(
               v11,
               L"mimeType",
               &v9,
               0,
               0);
        if ( v5 < 0 )
          break;
        v5 = MIME_MAP_TABLE::CreateAndAddMimeMapEntry(this, v9, v8);
        if ( v5 < 0 )
          break;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        ++v6;
        v11 = 0;
        if ( v6 >= v10 )
          goto LABEL_9;
      }
    }
  }
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v11 = 0;
  }
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180018778  mov     [rsp-18h+arg_0], rbx
0x18001877d  push    rbp
0x18001877e  push    rsi
0x18001877f  push    rdi
0x180018780  mov     rbp, rsp
0x180018783  sub     rsp, 40h
0x180018787  mov     rax, [rdx]
0x18001878a  mov     r8, rdx
0x18001878d  mov     rsi, rcx
0x180018790  mov     [rbp+arg_18], 0
0x180018798  lea     rdx, [rbp+arg_18]
0x18001879c  mov     [rbp+arg_10], 0
0x1800187a4  mov     rcx, r8
0x1800187a7  mov     [rbp+arg_8], 0
0x1800187ae  mov     rax, [rax+28h]
0x1800187b2  mov     [rbp+var_10], 0
0x1800187ba  mov     [rbp+var_8], 0
0x1800187c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187c7  mov     ebx, eax
0x1800187c9  test    eax, eax
0x1800187cb  js      loc_1800188C1
0x1800187d1  mov     rcx, [rbp+arg_18]
0x1800187d5  lea     rdx, [rbp+arg_8]
0x1800187d9  mov     rax, [rcx]
0x1800187dc  mov     rax, [rax+18h]
0x1800187e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187e5  mov     ebx, eax
0x1800187e7  test    eax, eax
0x1800187e9  js      loc_1800188C1
0x1800187ef  xor     edi, edi
0x1800187f1  cmp     [rbp+arg_8], edi
0x1800187f4  jbe     loc_1800188AD
0x1800187fa  mov     rcx, [rbp+arg_18]
0x1800187fe  lea     r8, [rbp+arg_10]
0x180018802  mov     edx, edi
0x180018804  mov     rax, [rcx]
0x180018807  mov     rax, [rax+20h]
0x18001880b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018810  mov     ebx, eax
0x180018812  test    eax, eax
0x180018814  js      loc_1800188C1
0x18001881a  mov     rcx, [rbp+arg_10]
0x18001881e  lea     r8, [rbp+var_10]
0x180018822  xor     r9d, r9d
0x180018825  mov     [rsp+40h+var_20], 0
0x18001882e  lea     rdx, aFileextension; "fileExtension"
0x180018835  mov     rax, [rcx]
0x180018838  mov     rax, [rax+40h]
0x18001883c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018841  mov     ebx, eax
0x180018843  test    eax, eax
0x180018845  js      short loc_1800188C1
0x180018847  mov     rcx, [rbp+arg_10]
0x18001884b  lea     r8, [rbp+var_8]
0x18001884f  xor     r9d, r9d
0x180018852  mov     [rsp+40h+var_20], 0
0x18001885b  lea     rdx, aMimetype; "mimeType"
0x180018862  mov     rax, [rcx]
0x180018865  mov     rax, [rax+40h]
0x180018869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001886e  mov     ebx, eax
0x180018870  test    eax, eax
0x180018872  js      short loc_1800188C1
0x180018874  mov     r8, [rbp+var_10]; unsigned __int16 *
0x180018878  mov     rcx, rsi; this
0x18001887b  mov     rdx, [rbp+var_8]; unsigned __int16 *
0x18001887f  call    ?CreateAndAddMimeMapEntry@MIME_MAP_TABLE@@AEAAJPEAG0@Z; MIME_MAP_TABLE::CreateAndAddMimeMapEntry(ushort *,ushort *)
0x180018884  mov     ebx, eax
0x180018886  test    eax, eax
0x180018888  js      short loc_1800188C1
0x18001888a  mov     rcx, [rbp+arg_10]
0x18001888e  mov     rax, [rcx]
0x180018891  mov     rax, [rax+10h]
0x180018895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001889a  inc     edi
0x18001889c  mov     [rbp+arg_10], 0
0x1800188a4  cmp     edi, [rbp+arg_8]
0x1800188a7  jb      loc_1800187FA
0x1800188ad  mov     rcx, [rbp+arg_18]
0x1800188b1  mov     rax, [rcx]
0x1800188b4  mov     rax, [rax+10h]
0x1800188b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800188bd  xor     eax, eax
0x1800188bf  jmp     short loc_1800188F5
0x1800188c1  mov     rcx, [rbp+arg_10]
0x1800188c5  test    rcx, rcx
0x1800188c8  jz      short loc_1800188DE
0x1800188ca  mov     rax, [rcx]
0x1800188cd  mov     rax, [rax+10h]
0x1800188d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800188d6  mov     [rbp+arg_10], 0
0x1800188de  mov     rcx, [rbp+arg_18]
0x1800188e2  test    rcx, rcx
0x1800188e5  jz      short loc_1800188F3
0x1800188e7  mov     rax, [rcx]
0x1800188ea  mov     rax, [rax+10h]
0x1800188ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800188f3  mov     eax, ebx
0x1800188f5  mov     rbx, [rsp+40h+arg_0]
0x1800188fa  add     rsp, 40h
0x1800188fe  pop     rdi
0x1800188ff  pop     rsi
0x180018900  pop     rbp
0x180018901  retn
```
