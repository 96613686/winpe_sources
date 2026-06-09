# CScaledResourceFactory::SetResource(HINSTANCE__ *,ushort const *)

- ea: `0x18002e710`
- end: `0x18002e765`
- name: `?SetResource@CScaledResourceFactory@@QEAAJPEAUHINSTANCE__@@PEBG@Z`
- size: `85`
- prototype: `__int64 __fastcall(CScaledResourceFactory *__hidden this, HINSTANCE, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002e284`

## callees

- `0x18002e710`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002e739`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002e739`

## string_xrefs

- `0x18002e732`: `imageres.dll`

## pseudocode

```c
__int64 __fastcall CScaledResourceFactory::SetResource(
        CScaledResourceFactory *this,
        HINSTANCE a2,
        const unsigned __int16 *a3)
{
  HMODULE ModuleHandleW; // rax
  unsigned int v6; // ebx

  ModuleHandleW = a2;
  v6 = -2147024809;
  if ( a2 || (ModuleHandleW = GetModuleHandleW(L"imageres.dll")) != 0 )
  {
    if ( a3 )
    {
      *((_QWORD *)this + 4) = ModuleHandleW;
      v6 = 0;
      *((_QWORD *)this + 5) = a3;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18002e710  mov     [rsp+arg_0], rbx
0x18002e715  mov     [rsp+arg_8], rsi
0x18002e71a  push    rdi
0x18002e71b  sub     rsp, 20h
0x18002e71f  mov     rdi, r8
0x18002e722  mov     rax, rdx
0x18002e725  mov     rsi, rcx
0x18002e728  mov     ebx, 80070057h
0x18002e72d  test    rdx, rdx
0x18002e730  jnz     short loc_18002E744
0x18002e732  lea     rcx, aImageresDll; "imageres.dll"
0x18002e739  call    cs:__imp_GetModuleHandleW
0x18002e73f  test    rax, rax
0x18002e742  jz      short loc_18002E753
0x18002e744  test    rdi, rdi
0x18002e747  jz      short loc_18002E753
0x18002e749  mov     [rsi+20h], rax
0x18002e74d  xor     ebx, ebx
0x18002e74f  mov     [rsi+28h], rdi
0x18002e753  mov     rsi, [rsp+28h+arg_8]
0x18002e758  mov     eax, ebx
0x18002e75a  mov     rbx, [rsp+28h+arg_0]
0x18002e75f  add     rsp, 20h
0x18002e763  pop     rdi
0x18002e764  retn
```
