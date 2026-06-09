# CMapBase<wchar_t *,Wsp::Health::CHealthConnection *>::Remove(wchar_t *)

- ea: `0x18007211c`
- end: `0x18007217e`
- name: `?Remove@?$CMapBase@PEA_WPEAVCHealthConnection@Health@Wsp@@@@QEAAHPEA_W@Z`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x1800721dc`

## callees

- `0x18007211c`

## import_xrefs

- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18007213f`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18007213f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180072164`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180072164`

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
0x18007211c  mov     rax, rsp
0x18007211f  mov     [rax+8], rbx
0x180072123  push    rdi
0x180072124  sub     rsp, 30h
0x180072128  mov     rbx, rcx
0x18007212b  mov     [rax-18h], rdx
0x18007212f  add     rcx, 8; Table
0x180072133  mov     qword ptr [rax-10h], 0
0x18007213b  lea     rdx, [rax-18h]; Buffer
0x18007213f  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180072146  nop     dword ptr [rax+rax+00h]
0x18007214b  movzx   edi, al
0x18007214e  test    al, al
0x180072150  jz      short loc_180072155
0x180072152  dec     dword ptr [rbx+70h]
0x180072155  mov     cl, dil
0x180072158  neg     cl
0x18007215a  sbb     ecx, ecx
0x18007215c  not     ecx
0x18007215e  and     ecx, 490h; dwErrCode
0x180072164  call    cs:__imp_SetLastError
0x18007216b  nop     dword ptr [rax+rax+00h]
0x180072170  mov     rbx, [rsp+38h+arg_0]
0x180072175  mov     eax, edi
0x180072177  add     rsp, 30h
0x18007217b  pop     rdi
0x18007217c  retn
```
