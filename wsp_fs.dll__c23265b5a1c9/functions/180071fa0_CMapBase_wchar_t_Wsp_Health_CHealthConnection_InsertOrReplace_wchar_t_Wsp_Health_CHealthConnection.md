# CMapBase<wchar_t *,Wsp::Health::CHealthConnection *>::InsertOrReplace(wchar_t *,Wsp::Health::CHealthConnection *)

- ea: `0x180071fa0`
- end: `0x18007201a`
- name: `?InsertOrReplace@?$CMapBase@PEA_WPEAVCHealthConnection@Health@Wsp@@@@UEAAJPEA_WPEAVCHealthConnection@Health@Wsp@@@Z`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180071f40`

## callees

- `0x180071fa0`

## import_xrefs

- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180071fc3`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180071fc3`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x180071fe3`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x180071fe3`

## pseudocode

```c
__int64 __fastcall CMapBase<wchar_t *,Wsp::Health::CHealthConnection *>::InsertOrReplace(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD Buffer[3]; // [rsp+20h] [rbp-18h] BYREF
  unsigned __int8 NewElement; // [rsp+40h] [rbp+8h] BYREF

  Buffer[0] = a2;
  Buffer[1] = a3;
  NewElement = 0;
  RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(a1 + 8), Buffer);
  if ( !RtlInsertElementGenericTableAvl((PRTL_AVL_TABLE)(a1 + 8), Buffer, 0x10u, &NewElement) )
    return 2147942414LL;
  if ( !NewElement )
    return 2147942583LL;
  ++*(_DWORD *)(a1 + 112);
  return 0;
}

```

## disassembly

```asm
0x180071fa0  mov     rax, rsp
0x180071fa3  mov     [rax+10h], rbx
0x180071fa7  push    rdi
0x180071fa8  sub     rsp, 30h
0x180071fac  mov     rdi, rcx
0x180071faf  mov     [rax-18h], rdx
0x180071fb3  lea     rdx, [rax-18h]; Buffer
0x180071fb7  mov     [rax-10h], r8
0x180071fbb  add     rcx, 8; Table
0x180071fbf  mov     byte ptr [rax+8], 0
0x180071fc3  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180071fca  nop     dword ptr [rax+rax+00h]
0x180071fcf  lea     r9, [rsp+38h+NewElement]; NewElement
0x180071fd4  mov     r8d, 10h; BufferSize
0x180071fda  lea     rdx, [rsp+38h+Buffer]; Buffer
0x180071fdf  lea     rcx, [rdi+8]; Table
0x180071fe3  call    cs:__imp_RtlInsertElementGenericTableAvl
0x180071fea  nop     dword ptr [rax+rax+00h]
0x180071fef  test    rax, rax
0x180071ff2  jnz     short loc_180071FFB
0x180071ff4  mov     eax, 8007000Eh
0x180071ff9  jmp     short loc_18007200E
0x180071ffb  cmp     [rsp+38h+NewElement], 0
0x180072000  jz      short loc_180072009
0x180072002  inc     dword ptr [rdi+70h]
0x180072005  xor     eax, eax
0x180072007  jmp     short loc_18007200E
0x180072009  mov     eax, 800700B7h
0x18007200e  mov     rbx, [rsp+38h+arg_8]
0x180072013  add     rsp, 30h
0x180072017  pop     rdi
0x180072018  retn
```
