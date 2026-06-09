# PxeDhcpAppendOptionRaw

- ea: `0x180007890`
- end: `0x180007979`
- name: `PxeDhcpAppendOptionRaw`
- size: `233`
- prototype: `DWORD __stdcall(PVOID pReplyPacket, ULONG uMaxReplyPacketLen, PULONG puReplyPacketLen, USHORT uBufferLen, PVOID pBuffer)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180007890`
- `0x180011a62`

## import_xrefs

- `WdsCommonLib!?Shutdown@CDhcpOptions@@QEAAKXZ` at `0x180007951`
- `WdsCommonLib!?Shutdown@CDhcpOptions@@QEAAKXZ` at `0x180007951`
- `WdsCommonLib!?CreateInitializeFromPacket@CDhcpOptions@@QEAAKPEAXKK@Z` at `0x180007903`
- `WdsCommonLib!?CreateInitializeFromPacket@CDhcpOptions@@QEAAKPEAXKK@Z` at `0x180007903`
- `WdsCommonLib!?AddOptionRaw@CDhcpOptions@@QEAAKGPEBX@Z` at `0x180007925`
- `WdsCommonLib!?AddOptionRaw@CDhcpOptions@@QEAAKGPEBX@Z` at `0x180007925`

## pseudocode

```c
DWORD __stdcall PxeDhcpAppendOptionRaw(
        PVOID pReplyPacket,
        ULONG uMaxReplyPacketLen,
        PULONG puReplyPacketLen,
        USHORT uBufferLen,
        PVOID pBuffer)
{
  ULONG v9; // r9d
  DWORD InitializeFromPacket; // ebx
  _BYTE v12[272]; // [rsp+20h] [rbp-138h] BYREF
  __int64 v13; // [rsp+130h] [rbp-28h]
  int v14; // [rsp+138h] [rbp-20h]
  int v15; // [rsp+13Ch] [rbp-1Ch]
  int v16; // [rsp+140h] [rbp-18h]

  v13 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  memset_0(v12, 0, sizeof(v12));
  if ( pReplyPacket
    && puReplyPacketLen
    && (v9 = *puReplyPacketLen, *puReplyPacketLen < uMaxReplyPacketLen)
    && v9 >= 0xF0 )
  {
    InitializeFromPacket = CDhcpOptions::CreateInitializeFromPacket(
                             (CDhcpOptions *)v12,
                             pReplyPacket,
                             uMaxReplyPacketLen,
                             v9 - 240);
    if ( !InitializeFromPacket )
    {
      InitializeFromPacket = CDhcpOptions::AddOptionRaw((CDhcpOptions *)v12, uBufferLen, pBuffer);
      if ( !InitializeFromPacket )
        *puReplyPacketLen = v15 + 240;
    }
  }
  else
  {
    InitializeFromPacket = 87;
  }
  CDhcpOptions::Shutdown((CDhcpOptions *)v12);
  return InitializeFromPacket;
}

```

## disassembly

```asm
0x180007890  mov     rax, rsp
0x180007893  mov     [rax+8], rbx
0x180007897  mov     [rax+10h], rbp
0x18000789b  mov     [rax+18h], rsi
0x18000789f  push    rdi
0x1800078a0  sub     rsp, 150h
0x1800078a7  and     qword ptr [rax-28h], 0
0x1800078ac  mov     rdi, r8
0x1800078af  and     dword ptr [rax-20h], 0
0x1800078b3  mov     ebx, edx
0x1800078b5  and     dword ptr [rax-1Ch], 0
0x1800078b9  mov     rsi, rcx
0x1800078bc  and     dword ptr [rax-18h], 0
0x1800078c0  lea     rcx, [rsp+158h+var_138]; void *
0x1800078c5  xor     edx, edx; Val
0x1800078c7  mov     r8d, 110h; Size
0x1800078cd  movzx   ebp, r9w
0x1800078d1  call    memset_0
0x1800078d6  test    rsi, rsi
0x1800078d9  jz      short loc_180007947
0x1800078db  test    rdi, rdi
0x1800078de  jz      short loc_180007947
0x1800078e0  mov     r9d, [rdi]
0x1800078e3  cmp     r9d, ebx
0x1800078e6  jnb     short loc_180007947
0x1800078e8  cmp     r9d, 0F0h
0x1800078ef  jb      short loc_180007947
0x1800078f1  add     r9d, 0FFFFFF10h
0x1800078f8  lea     rcx, [rsp+158h+var_138]
0x1800078fd  mov     r8d, ebx
0x180007900  mov     rdx, rsi
0x180007903  call    cs:__imp_?CreateInitializeFromPacket@CDhcpOptions@@QEAAKPEAXKK@Z; CDhcpOptions::CreateInitializeFromPacket(void *,ulong,ulong)
0x18000790a  nop     dword ptr [rax+rax+00h]
0x18000790f  mov     ebx, eax
0x180007911  test    eax, eax
0x180007913  jnz     short loc_18000794C
0x180007915  mov     r8, [rsp+158h+pBuffer]
0x18000791d  lea     rcx, [rsp+158h+var_138]
0x180007922  movzx   edx, bp
0x180007925  call    cs:__imp_?AddOptionRaw@CDhcpOptions@@QEAAKGPEBX@Z; CDhcpOptions::AddOptionRaw(ushort,void const *)
0x18000792c  nop     dword ptr [rax+rax+00h]
0x180007931  mov     ebx, eax
0x180007933  test    eax, eax
0x180007935  jnz     short loc_18000794C
0x180007937  mov     eax, [rsp+158h+var_1C]
0x18000793e  add     eax, 0F0h
0x180007943  mov     [rdi], eax
0x180007945  jmp     short loc_18000794C
0x180007947  mov     ebx, 57h ; 'W'
0x18000794c  lea     rcx, [rsp+158h+var_138]
0x180007951  call    cs:__imp_?Shutdown@CDhcpOptions@@QEAAKXZ; CDhcpOptions::Shutdown(void)
0x180007958  nop     dword ptr [rax+rax+00h]
0x18000795d  lea     r11, [rsp+158h+var_8]
0x180007965  mov     eax, ebx
0x180007967  mov     rbx, [r11+10h]
0x18000796b  mov     rbp, [r11+18h]
0x18000796f  mov     rsi, [r11+20h]
0x180007973  mov     rsp, r11
0x180007976  pop     rdi
0x180007977  retn
```
