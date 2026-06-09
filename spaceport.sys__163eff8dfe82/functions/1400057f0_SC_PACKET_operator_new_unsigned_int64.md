# SC_PACKET::operator new(unsigned __int64)

- ea: `0x1400057f0`
- end: `0x14000588d`
- name: `??2SC_PACKET@@SAPEAX_K@Z`
- size: `157`
- prototype: `void *__fastcall(SIZE_T NumberOfBytes)`
- caller_count: `22`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140004250`
- `0x1400063f0`
- `0x140007010`
- `0x1400073c0`
- `0x140007530`
- `0x14000a5d0`
- `0x1400116e0`
- `0x140027d70`
- `0x14002f858`
- `0x140037a8c`
- `0x140045234`
- `0x140045664`
- `0x140049cb0`
- `0x14004d9a8`
- `0x14004e140`
- `0x14004e9b0`
- `0x14004f580`
- `0x140050c80`
- `0x14005116c`
- `0x140052bd0`
- `0x14009cdc0`
- `0x1400b0f48`

## callees

- `0x1400057f0`
- `0x1400058a0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000584a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000584a`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000581e`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000581e`

## pseudocode

```c
_BYTE *__fastcall SC_PACKET::operator new(SIZE_T NumberOfBytes)
{
  unsigned int v2; // ebx
  ULONG v3; // edx
  char v4; // bl
  _BYTE *result; // rax

  if ( *((_BYTE *)WPP_MAIN_CB.DeviceExtension + 435) || NumberOfBytes > 0x128 )
  {
    v4 = -1;
  }
  else
  {
    v2 = *((_DWORD *)WPP_MAIN_CB.DeviceExtension + 84);
    v3 = KeGetCurrentProcessorNumberEx(0) % v2;
    v4 = v3;
    if ( (_BYTE)v3 != 0xFF )
    {
      result = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*((_QWORD *)WPP_MAIN_CB.DeviceExtension + 43)
                                                                        + ((unsigned __int64)(unsigned __int8)v3 << 7)));
      goto LABEL_5;
    }
  }
  result = SP_CONTROL::AllocatePacket((POOL_TYPE)512, NumberOfBytes, 0x4B507053u);
LABEL_5:
  if ( result )
  {
    result[171] = v4;
    *((_WORD *)result + 86) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400057f0  mov     [rsp+arg_0], rbx
0x1400057f5  push    rdi
0x1400057f6  sub     rsp, 20h
0x1400057fa  mov     rbx, cs:WPP_MAIN_CB.DeviceExtension
0x140005801  mov     rdi, rcx
0x140005804  cmp     byte ptr [rbx+1B3h], 0
0x14000580b  jnz     short loc_140005876
0x14000580d  cmp     rcx, 128h
0x140005814  ja      short loc_140005876
0x140005816  mov     ebx, [rbx+150h]
0x14000581c  xor     ecx, ecx; ProcNumber
0x14000581e  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140005825  nop     dword ptr [rax+rax+00h]
0x14000582a  xor     edx, edx
0x14000582c  div     ebx
0x14000582e  mov     ebx, edx
0x140005830  cmp     dl, 0FFh
0x140005833  jz      short loc_140005878
0x140005835  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x14000583c  movzx   ecx, bl
0x14000583f  shl     rcx, 7
0x140005843  add     rcx, [rax+158h]; Lookaside
0x14000584a  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140005851  nop     dword ptr [rax+rax+00h]
0x140005856  test    rax, rax
0x140005859  jz      short loc_14000586A
0x14000585b  mov     [rax+0ABh], bl
0x140005861  mov     word ptr [rax+0ACh], 0
0x14000586a  mov     rbx, [rsp+28h+arg_0]
0x14000586f  add     rsp, 20h
0x140005873  pop     rdi
0x140005874  retn
0x140005876  mov     bl, 0FFh
0x140005878  mov     r8d, 4B507053h; Tag
0x14000587e  mov     rdx, rdi; NumberOfBytes
0x140005881  mov     ecx, 200h; PoolType
0x140005886  call    ?AllocatePacket@SP_CONTROL@@SAPEAXW4_POOL_TYPE@@_KK@Z; SP_CONTROL::AllocatePacket(_POOL_TYPE,unsigned __int64,ulong)
0x14000588b  jmp     short loc_140005856
```
