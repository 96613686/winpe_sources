# CMapBase<wchar_t *,Wsp::Health::CHealthConnection *>::Remove(wchar_t *)

- ea: `0x18007067c`
- end: `0x1800706d1`
- name: `?Remove@?$CMapBase@PEA_WPEAVCHealthConnection@Health@Wsp@@@@QEAAHPEA_W@Z`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x180070724`

## callees

- `0x18007067c`

## import_xrefs

- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18007069f`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18007069f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800706be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800706be`

## pseudocode

```c
__int64 __fastcall CMapBase<wchar_t *,Wsp::Health::CHealthConnection *>::Remove(__int64 a1, __int64 a2)
{
  BOOLEAN v3; // al
  unsigned int v4; // edi
  _QWORD v6[3]; // [rsp+20h] [rbp-18h] BYREF

  v6[0] = a2;
  v6[1] = 0;
  v3 = RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(a1 + 8), v6);
  v4 = v3;
  if ( v3 )
    --*(_DWORD *)(a1 + 112);
  SetLastError(v3 == 0 ? 0x490 : 0);
  return v4;
}

```

## disassembly

```asm
0x18007067c  mov     rax, rsp
0x18007067f  mov     [rax+8], rbx
0x180070683  push    rdi
0x180070684  sub     rsp, 30h
0x180070688  mov     rbx, rcx
0x18007068b  mov     [rax-18h], rdx
0x18007068f  add     rcx, 8; Table
0x180070693  mov     qword ptr [rax-10h], 0
0x18007069b  lea     rdx, [rax-18h]; Buffer
0x18007069f  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1800706a5  movzx   edi, al
0x1800706a8  test    al, al
0x1800706aa  jz      short loc_1800706AF
0x1800706ac  dec     dword ptr [rbx+70h]
0x1800706af  mov     cl, dil
0x1800706b2  neg     cl
0x1800706b4  sbb     ecx, ecx
0x1800706b6  not     ecx
0x1800706b8  and     ecx, 490h; dwErrCode
0x1800706be  call    cs:__imp_SetLastError
0x1800706c4  mov     rbx, [rsp+38h+arg_0]
0x1800706c9  mov     eax, edi
0x1800706cb  add     rsp, 30h
0x1800706cf  pop     rdi
0x1800706d0  retn
```
