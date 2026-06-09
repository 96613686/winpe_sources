# PxeDhcpAppendOption

- ea: `0x180007790`
- end: `0x180007881`
- name: `PxeDhcpAppendOption`
- size: `241`
- prototype: `DWORD __stdcall(PVOID pReplyPacket, ULONG uMaxReplyPacketLen, PULONG puReplyPacketLen, BYTE bOption, BYTE bOptionLen, PVOID pValue)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000eecc`

## callees

- `0x180007790`
- `0x180011a62`

## import_xrefs

- `WdsCommonLib!?Shutdown@CDhcpOptions@@QEAAKXZ` at `0x180007859`
- `WdsCommonLib!?Shutdown@CDhcpOptions@@QEAAKXZ` at `0x180007859`
- `WdsCommonLib!?CreateInitializeFromPacket@CDhcpOptions@@QEAAKPEAXKK@Z` at `0x180007802`
- `WdsCommonLib!?CreateInitializeFromPacket@CDhcpOptions@@QEAAKPEAXKK@Z` at `0x180007802`
- `WdsCommonLib!?AddOption@CDhcpOptions@@QEAAKEKPEBX@Z` at `0x18000782d`
- `WdsCommonLib!?AddOption@CDhcpOptions@@QEAAKEKPEBX@Z` at `0x18000782d`

## pseudocode

```c
DWORD __stdcall PxeDhcpAppendOption(
        PVOID pReplyPacket,
        ULONG uMaxReplyPacketLen,
        PULONG puReplyPacketLen,
        BYTE bOption,
        BYTE bOptionLen,
        PVOID pValue)
{
  ULONG v10; // r9d
  DWORD InitializeFromPacket; // ebx
  _BYTE v13[272]; // [rsp+20h] [rbp-138h] BYREF
  __int64 v14; // [rsp+130h] [rbp-28h]
  int v15; // [rsp+138h] [rbp-20h]
  int v16; // [rsp+13Ch] [rbp-1Ch]
  int v17; // [rsp+140h] [rbp-18h]

  v14 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  memset_0(v13, 0, sizeof(v13));
  if ( pReplyPacket
    && puReplyPacketLen
    && (v10 = *puReplyPacketLen, *puReplyPacketLen < uMaxReplyPacketLen)
    && v10 >= 0xF0 )
  {
    InitializeFromPacket = CDhcpOptions::CreateInitializeFromPacket(
                             (CDhcpOptions *)v13,
                             pReplyPacket,
                             uMaxReplyPacketLen,
                             v10 - 240);
    if ( !InitializeFromPacket )
    {
      InitializeFromPacket = CDhcpOptions::AddOption((CDhcpOptions *)v13, bOption, bOptionLen, pValue);
      if ( !InitializeFromPacket )
        *puReplyPacketLen = v16 + 240;
    }
  }
  else
  {
    InitializeFromPacket = 87;
  }
  CDhcpOptions::Shutdown((CDhcpOptions *)v13);
  return InitializeFromPacket;
}

```

## disassembly

```asm
0x180007790  mov     rax, rsp
0x180007793  mov     [rax+8], rbx
0x180007797  mov     [rax+10h], rbp
0x18000779b  mov     [rax+18h], rsi
0x18000779f  push    rdi
0x1800077a0  sub     rsp, 150h
0x1800077a7  and     qword ptr [rax-28h], 0
0x1800077ac  mov     rdi, r8
0x1800077af  and     dword ptr [rax-20h], 0
0x1800077b3  mov     ebx, edx
0x1800077b5  and     dword ptr [rax-1Ch], 0
0x1800077b9  mov     rsi, rcx
0x1800077bc  and     dword ptr [rax-18h], 0
0x1800077c0  lea     rcx, [rsp+158h+var_138]; void *
0x1800077c5  xor     edx, edx; Val
0x1800077c7  mov     r8d, 110h; Size
0x1800077cd  mov     bpl, r9b
0x1800077d0  call    memset_0
0x1800077d5  test    rsi, rsi
0x1800077d8  jz      short loc_18000784F
0x1800077da  test    rdi, rdi
0x1800077dd  jz      short loc_18000784F
0x1800077df  mov     r9d, [rdi]
0x1800077e2  cmp     r9d, ebx
0x1800077e5  jnb     short loc_18000784F
0x1800077e7  cmp     r9d, 0F0h
0x1800077ee  jb      short loc_18000784F
0x1800077f0  add     r9d, 0FFFFFF10h
0x1800077f7  lea     rcx, [rsp+158h+var_138]
0x1800077fc  mov     r8d, ebx
0x1800077ff  mov     rdx, rsi
0x180007802  call    cs:__imp_?CreateInitializeFromPacket@CDhcpOptions@@QEAAKPEAXKK@Z; CDhcpOptions::CreateInitializeFromPacket(void *,ulong,ulong)
0x180007809  nop     dword ptr [rax+rax+00h]
0x18000780e  mov     ebx, eax
0x180007810  test    eax, eax
0x180007812  jnz     short loc_180007854
0x180007814  movzx   r8d, [rsp+158h+bOptionLen]
0x18000781d  lea     rcx, [rsp+158h+var_138]
0x180007822  mov     r9, [rsp+158h+pValue]
0x18000782a  mov     dl, bpl
0x18000782d  call    cs:__imp_?AddOption@CDhcpOptions@@QEAAKEKPEBX@Z; CDhcpOptions::AddOption(uchar,ulong,void const *)
0x180007834  nop     dword ptr [rax+rax+00h]
0x180007839  mov     ebx, eax
0x18000783b  test    eax, eax
0x18000783d  jnz     short loc_180007854
0x18000783f  mov     eax, [rsp+158h+var_1C]
0x180007846  add     eax, 0F0h
0x18000784b  mov     [rdi], eax
0x18000784d  jmp     short loc_180007854
0x18000784f  mov     ebx, 57h ; 'W'
0x180007854  lea     rcx, [rsp+158h+var_138]
0x180007859  call    cs:__imp_?Shutdown@CDhcpOptions@@QEAAKXZ; CDhcpOptions::Shutdown(void)
0x180007860  nop     dword ptr [rax+rax+00h]
0x180007865  lea     r11, [rsp+158h+var_8]
0x18000786d  mov     eax, ebx
0x18000786f  mov     rbx, [r11+10h]
0x180007873  mov     rbp, [r11+18h]
0x180007877  mov     rsi, [r11+20h]
0x18000787b  mov     rsp, r11
0x18000787e  pop     rdi
0x18000787f  retn
```
