# CMapBase<wchar_t *,Wsp::Health::CHealthConnection *>::InsertOrReplace(wchar_t *,Wsp::Health::CHealthConnection *)

- ea: `0x180079850`
- end: `0x1800798bd`
- name: `?InsertOrReplace@?$CMapBase@PEA_WPEAVCHealthConnection@Health@Wsp@@@@UEAAJPEA_WPEAVCHealthConnection@Health@Wsp@@@Z`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800797f0`

## callees

- `0x180079850`

## import_xrefs

- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180079873`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180079873`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18007988d`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18007988d`

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
0x180079850  mov     rax, rsp
0x180079853  mov     [rax+10h], rbx
0x180079857  push    rdi
0x180079858  sub     rsp, 30h
0x18007985c  mov     rdi, rcx
0x18007985f  mov     [rax-18h], rdx
0x180079863  lea     rdx, [rax-18h]; Buffer
0x180079867  mov     [rax-10h], r8
0x18007986b  add     rcx, 8; Table
0x18007986f  mov     byte ptr [rax+8], 0
0x180079873  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180079879  lea     r9, [rsp+38h+NewElement]; NewElement
0x18007987e  mov     r8d, 10h; BufferSize
0x180079884  lea     rdx, [rsp+38h+Buffer]; Buffer
0x180079889  lea     rcx, [rdi+8]; Table
0x18007988d  call    cs:__imp_RtlInsertElementGenericTableAvl
0x180079893  test    rax, rax
0x180079896  jnz     short loc_18007989F
0x180079898  mov     eax, 8007000Eh
0x18007989d  jmp     short loc_1800798B2
0x18007989f  cmp     [rsp+38h+NewElement], 0
0x1800798a4  jz      short loc_1800798AD
0x1800798a6  inc     dword ptr [rdi+70h]
0x1800798a9  xor     eax, eax
0x1800798ab  jmp     short loc_1800798B2
0x1800798ad  mov     eax, 800700B7h
0x1800798b2  mov     rbx, [rsp+38h+arg_8]
0x1800798b7  add     rsp, 30h
0x1800798bb  pop     rdi
0x1800798bc  retn
```
