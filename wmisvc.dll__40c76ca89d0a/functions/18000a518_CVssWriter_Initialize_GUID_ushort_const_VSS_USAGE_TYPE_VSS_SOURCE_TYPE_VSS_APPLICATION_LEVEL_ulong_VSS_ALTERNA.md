# CVssWriter::Initialize(_GUID,ushort const *,VSS_USAGE_TYPE,VSS_SOURCE_TYPE,_VSS_APPLICATION_LEVEL,ulong,VSS_ALTERNATE_WRITER_STATE,bool,ushort const *)

- ea: `0x18000a518`
- end: `0x18000a5d9`
- name: `?Initialize@CVssWriter@@QEAAJU_GUID@@PEBGW4VSS_USAGE_TYPE@@W4VSS_SOURCE_TYPE@@W4_VSS_APPLICATION_LEVEL@@KW4VSS_ALTERNATE_WRITER_STATE@@_N1@Z`
- size: `193`
- prototype: `__int64 __fastcall(__int64, __int128 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a3cc`

## callees

- `0x18000a518`
- `0x180020010`

## import_xrefs

- `ext-ms-win-fs-vssapi-l1-1-0!CreateWriter` at `0x18000a53f`
- `ext-ms-win-fs-vssapi-l1-1-0!CreateWriter` at `0x18000a53f`

## string_xrefs

- `0x18000a54c`: `WMI Writer`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CVssWriter::Initialize(__int64 a1, __int128 *a2)
{
  _QWORD *v2; // rbx
  __int64 result; // rax
  __int64 v5; // rcx
  __int64 (__fastcall *v6)(__int64, __int128 *, const wchar_t *, _QWORD, _DWORD, _DWORD, int, int, int, int, int, char); // rax
  int v7; // edi
  char v8; // [rsp+58h] [rbp-30h]
  __int128 v9; // [rsp+70h] [rbp-18h] BYREF

  v2 = (_QWORD *)(a1 + 8);
  if ( *(_QWORD *)(a1 + 8) )
    return 2147500037LL;
  result = CreateWriter(a1, a1 + 8);
  if ( (int)result >= 0 )
  {
    v5 = *v2;
    v8 = 0;
    v6 = *(__int64 (__fastcall **)(__int64, __int128 *, const wchar_t *, _QWORD, _DWORD, _DWORD, int, int, int, int, int, char))(*(_QWORD *)*v2 + 24LL);
    v9 = *a2;
    v7 = v6(v5, &v9, L"WMI Writer", 0, 0, 0, 2, 3, 3, 60000, 1, v8);
    if ( v7 < 0 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 16LL))(*v2);
      *v2 = 0;
    }
    return (unsigned int)v7;
  }
  return result;
}

```

## disassembly

```asm
0x18000a518  mov     [rsp+arg_0], rbx
0x18000a51d  push    rdi
0x18000a51e  sub     rsp, 80h
0x18000a525  lea     rbx, [rcx+8]
0x18000a529  mov     rdi, rdx
0x18000a52c  cmp     qword ptr [rbx], 0
0x18000a530  jz      short loc_18000A53C
0x18000a532  mov     eax, 80004005h
0x18000a537  jmp     loc_18000A5C8
0x18000a53c  mov     rdx, rbx
0x18000a53f  call    cs:__imp_CreateWriter
0x18000a545  test    eax, eax
0x18000a547  js      short loc_18000A5C8
0x18000a549  mov     rcx, [rbx]
0x18000a54c  lea     r8, aWmiWriter; "WMI Writer"
0x18000a553  movaps  xmm0, xmmword ptr [rdi]
0x18000a556  mov     edx, 3
0x18000a55b  mov     [rsp+88h+var_30], 0
0x18000a560  xor     r9d, r9d
0x18000a563  mov     [rsp+88h+var_38], 1
0x18000a56b  mov     rax, [rcx]
0x18000a56e  mov     [rsp+88h+var_40], 0EA60h
0x18000a576  mov     [rsp+88h+var_48], edx
0x18000a57a  mov     [rsp+88h+var_50], edx
0x18000a57e  lea     rdx, [rsp+88h+var_18]
0x18000a583  mov     rax, [rax+18h]
0x18000a587  mov     [rsp+88h+var_58], 2
0x18000a58f  mov     [rsp+88h+var_60], 0
0x18000a597  movdqa  [rsp+88h+var_18], xmm0
0x18000a59d  mov     [rsp+88h+var_68], 0
0x18000a5a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5aa  mov     edi, eax
0x18000a5ac  test    eax, eax
0x18000a5ae  jns     short loc_18000A5C6
0x18000a5b0  mov     rcx, [rbx]
0x18000a5b3  mov     rdx, [rcx]
0x18000a5b6  mov     rax, [rdx+10h]
0x18000a5ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5bf  mov     qword ptr [rbx], 0
0x18000a5c6  mov     eax, edi
0x18000a5c8  mov     rbx, [rsp+88h+arg_0]
0x18000a5d0  add     rsp, 80h
0x18000a5d7  pop     rdi
0x18000a5d8  retn
```
