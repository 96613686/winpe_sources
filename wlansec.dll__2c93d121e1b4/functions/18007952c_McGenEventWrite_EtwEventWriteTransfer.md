# McGenEventWrite_EtwEventWriteTransfer

- ea: `0x18007952c`
- end: `0x180079585`
- name: `McGenEventWrite_EtwEventWriteTransfer`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000e6e0`
- `0x18007958c`

## callees

- `0x18007952c`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180079573`
- `ntdll!EtwEventWriteTransfer` at `0x180079573`

## pseudocode

```c
__int64 __fastcall McGenEventWrite_EtwEventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, int a4, __int64 a5)
{
  unsigned __int16 *v5; // rcx
  int v6; // r8d

  v5 = (unsigned __int16 *)qword_1800AE2C8;
  if ( qword_1800AE2C8 )
  {
    *(_QWORD *)a5 = qword_1800AE2C8;
    v6 = 2;
    LODWORD(v5) = *v5;
  }
  else
  {
    *(_QWORD *)a5 = 0;
    v6 = 0;
  }
  *(_DWORD *)(a5 + 8) = (_DWORD)v5;
  *(_DWORD *)(a5 + 12) = v6;
  return EtwEventWriteTransfer(WLANSVC_EVT_GUID_Context, a2, 0, 0, a4, a5);
}

```

## disassembly

```asm
0x18007952c  sub     rsp, 38h
0x180079530  mov     rcx, cs:qword_1800AE2C8
0x180079537  mov     rax, [rsp+38h+arg_20]
0x18007953c  test    rcx, rcx
0x18007953f  jnz     short loc_180079549
0x180079541  mov     [rax], rcx
0x180079544  xor     r8d, r8d
0x180079547  jmp     short loc_180079555
0x180079549  mov     [rax], rcx
0x18007954c  mov     r8d, 2
0x180079552  movzx   ecx, word ptr [rcx]
0x180079555  mov     [rax+8], ecx
0x180079558  mov     [rax+0Ch], r8d
0x18007955c  xor     r8d, r8d
0x18007955f  mov     rcx, cs:WLANSVC_EVT_GUID_Context
0x180079566  mov     [rsp+38h+var_10], rax
0x18007956b  mov     [rsp+38h+var_18], r9d
0x180079570  xor     r9d, r9d
0x180079573  call    cs:__imp_EtwEventWriteTransfer
0x18007957a  nop     dword ptr [rax+rax+00h]
0x18007957f  add     rsp, 38h
0x180079583  retn
```
