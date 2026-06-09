# Srv2DecompressDecryptedReceiveHandler

- ea: `0x140019168`
- end: `0x140019245`
- name: `Srv2DecompressDecryptedReceiveHandler`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400749c0`

## callees

- `0x140004960`
- `0x140005070`
- `0x140019168`
- `0x1400225c4`
- `0x140022f0c`

## import_xrefs

- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1400191fe`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1400191fe`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003d140`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003d140`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14001921a`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14001921a`

## string_xrefs

- `0x1400191df`: `Srv2PostToThreadPool`

## pseudocode

```c
__int64 __fastcall Srv2DecompressDecryptedReceiveHandler(__int64 a1, __int64 a2, _BYTE *a3)
{
  __int64 v3; // rax
  __int64 result; // rax
  bool v8; // zf
  __int64 v9; // rbx
  __int64 v10; // rbx
  __int64 v11; // rdx
  __int64 v12; // r8
  unsigned int v13; // ebx
  char v14; // [rsp+20h] [rbp-18h]

  v3 = *(_QWORD *)(a1 + 304);
  *a3 = 0;
  if ( **(_DWORD **)(v3 + 24) != 1112364028 )
    return 0;
  if ( KeGetCurrentIrql() > 1u )
  {
    v8 = *(_DWORD *)(a1 + 8) == 5;
    *(_QWORD *)(a1 + 48) = Srv2DecompressMessageWorker;
    *(_QWORD *)(a1 + 256) = a2;
    *(_DWORD *)(a1 + 72) = 0;
    if ( v8 )
    {
      v14 = 1;
      LOBYTE(v11) = 1;
      SRV2_PERF_ENTER_EX(a1 + 584, v11, 391, "Srv2PostToThreadPool", v14);
    }
    v9 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 136LL);
    v10 = *(_QWORD *)(v9 + 8LL * KeGetCurrentNodeNumber() + 8);
    if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)(v10 + 16), (PSLIST_ENTRY)(a1 + 32)) && *(_WORD *)(v10 + 66) )
      RfspThreadPoolNodeWakeIdleWorker((struct _KEVENT *)v10);
    *a3 = 1;
    return 0;
  }
  result = Srv2DecompressData((_QWORD *)a1, v11, v12);
  v13 = result;
  if ( (int)result >= 0 )
  {
    *(_DWORD *)(a1 + 484) |= 0x40u;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_dq(
          WPP_GLOBAL_Control->AttachedDevice,
          27,
          WPP_8c61ecf697593902513841fcaa61ed76_Traceguids,
          (unsigned int)result,
          *(_QWORD *)(a1 + 96));
    }
    return v13;
  }
  return result;
}

```

## disassembly

```asm
0x140019168  mov     [rsp+arg_0], rbx
0x14001916d  mov     [rsp+arg_8], rsi
0x140019172  push    rdi
0x140019173  sub     rsp, 30h
0x140019177  mov     rax, [rcx+130h]
0x14001917e  mov     rsi, r8
0x140019181  mov     rbx, rdx
0x140019184  mov     byte ptr [r8], 0
0x140019188  mov     rdi, rcx
0x14001918b  mov     r9, [rax+18h]
0x14001918f  cmp     dword ptr [r9], 424D53FCh
0x140019196  jz      loc_14003D140
0x14001919c  xor     eax, eax
0x14001919e  mov     rbx, [rsp+38h+arg_0]
0x1400191a3  mov     rsi, [rsp+38h+arg_8]
0x1400191a8  add     rsp, 30h
0x1400191ac  pop     rdi
0x1400191ad  retn
0x1400191af  mov     byte ptr [rsi], 1
0x1400191b2  jmp     short loc_14001919C
0x1400191b4  cmp     dword ptr [rdi+8], 5
0x1400191b8  lea     rax, Srv2DecompressMessageWorker
0x1400191bf  mov     [rdi+30h], rax
0x1400191c3  mov     [rdi+100h], rbx
0x1400191ca  mov     dword ptr [rdi+48h], 0
0x1400191d1  jnz     short loc_1400191F3
0x1400191d3  lea     rcx, [rdi+248h]
0x1400191da  mov     [rsp+38h+var_18], 1
0x1400191df  lea     r9, SourceString; "Srv2PostToThreadPool"
0x1400191e6  mov     r8d, 187h
0x1400191ec  mov     dl, 1
0x1400191ee  call    SRV2_PERF_ENTER_EX
0x1400191f3  mov     rax, [rdi+40h]
0x1400191f7  mov     rbx, [rax+88h]
0x1400191fe  call    cs:__imp_KeGetCurrentNodeNumber
0x140019205  nop     dword ptr [rax+rax+00h]
0x14001920a  movzx   eax, ax
0x14001920d  lea     rdx, [rdi+20h]; ListEntry
0x140019211  mov     rbx, [rbx+rax*8+8]
0x140019216  lea     rcx, [rbx+10h]; ListHead
0x14001921a  call    cs:__imp_ExpInterlockedPushEntrySList
0x140019221  nop     dword ptr [rax+rax+00h]
0x140019226  test    rax, rax
0x140019229  jnz     short loc_1400191AF
0x14001922b  movzx   edx, word ptr [rbx+42h]
0x14001922f  cmp     ax, dx
0x140019232  jz      loc_1400191AF
0x140019238  mov     rcx, rbx
0x14001923b  call    RfspThreadPoolNodeWakeIdleWorker
0x140019240  jmp     loc_1400191AF
0x14003d140  call    cs:__imp_KeGetCurrentIrql
0x14003d147  nop     dword ptr [rax+rax+00h]
0x14003d14c  cmp     al, 1
0x14003d14e  ja      loc_1400191B4
0x14003d154  mov     rcx, rdi
0x14003d157  call    Srv2DecompressData
0x14003d15c  mov     ebx, eax
0x14003d15e  test    eax, eax
0x14003d160  jns     short loc_14003D1AC
0x14003d162  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d169  lea     rax, WPP_GLOBAL_Control
0x14003d170  cmp     rcx, rax
0x14003d173  jz      short loc_14003D1A5
0x14003d175  test    dword ptr [rcx+2Ch], 200h
0x14003d17c  jz      short loc_14003D1A5
0x14003d17e  cmp     byte ptr [rcx+29h], 1
0x14003d182  jb      short loc_14003D1A5
0x14003d184  mov     rax, [rdi+60h]
0x14003d188  lea     r8, WPP_8c61ecf697593902513841fcaa61ed76_Traceguids
0x14003d18f  mov     rcx, [rcx+18h]
0x14003d193  mov     edx, 1Bh
0x14003d198  mov     r9d, ebx
0x14003d19b  mov     qword ptr [rsp+38h+var_18], rax
0x14003d1a0  call    WPP_SF_dq
0x14003d1a5  mov     eax, ebx
0x14003d1a7  jmp     loc_14001919E
0x14003d1ac  or      dword ptr [rdi+1E4h], 40h
0x14003d1b3  jmp     loc_14001919E
```
