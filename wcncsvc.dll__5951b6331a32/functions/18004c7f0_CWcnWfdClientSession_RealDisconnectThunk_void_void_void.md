# CWcnWfdClientSession::RealDisconnectThunk(void *,void *,void *)

- ea: `0x18004c7f0`
- end: `0x18004c945`
- name: `?RealDisconnectThunk@CWcnWfdClientSession@@CAXPEAX00@Z`
- size: `341`
- prototype: `void __fastcall(void *, void *, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180004f2c`
- `0x180015db4`
- `0x18004c7f0`
- `0x1800504cc`
- `0x180056de6`
- `0x180056dfe`

## import_xrefs

- `wlanapi!WlanQueryInterface` at `0x18004c843`
- `wlanapi!WlanQueryInterface` at `0x18004c843`
- `wlanapi!WlanDisconnect` at `0x18004c8b3`
- `wlanapi!WlanDisconnect` at `0x18004c8b3`
- `wlanapi!WlanFreeMemory` at `0x18004c915`
- `wlanapi!WlanFreeMemory` at `0x18004c915`

## string_xrefs

- `0x18004c872`: `WCN Temporary Profile`

## pseudocode

```c
void __fastcall CWcnWfdClientSession::RealDisconnectThunk(void *a1, char *a2, void *a3)
{
  void *v3; // rcx
  _DWORD *v5; // rbx
  unsigned int v6; // eax
  signed int v7; // eax
  unsigned int v8; // ecx
  CWcnSession *v9; // rcx
  DWORD v10; // [rsp+58h] [rbp+10h] BYREF
  PVOID pMemory; // [rsp+68h] [rbp+20h] BYREF

  v3 = (void *)*((_QWORD *)a2 + 7);
  pMemory = 0;
  if ( !v3 )
    return;
  v10 = 0;
  if ( WlanQueryInterface(v3, (const GUID *)a2 + 4, wlan_intf_opcode_current_connection, 0, &v10, &pMemory, 0) )
    goto LABEL_14;
  *((_WORD *)pMemory + 259) = 0;
  v5 = pMemory;
  if ( *((_DWORD *)pMemory + 1) == 1 && !wcscmp_0((const wchar_t *)pMemory + 4, L"WCN Temporary Profile") )
  {
    v6 = *((_DWORD *)a2 + 20);
    if ( v5[130] == v6 && !memcmp_0(v5 + 131, a2 + 84, v6) )
    {
      v7 = WlanDisconnect(*((HANDLE *)a2 + 7), (const GUID *)a2 + 4, 0);
      if ( v7 )
      {
        v8 = v7 > 0 ? (unsigned __int16)v7 | 0x80070000 : v7;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            46,
            WPP_16f86085a523394303ca33111ba71bc3_Traceguids,
            (unsigned int)v7,
            v8 | 0x80000000);
      }
LABEL_14:
      v5 = pMemory;
    }
  }
  if ( v5 )
    WlanFreeMemory(v5);
  WcnWlanCloseHandle(*((HANDLE *)a2 + 7));
  v9 = (CWcnSession *)*((_QWORD *)a2 + 2);
  *((_QWORD *)a2 + 7) = 0;
  CWcnSession::FinishDisconnect(v9);
}

```

## disassembly

```asm
0x18004c7f0  mov     r11, rsp
0x18004c7f3  mov     [r11+8], rbx
0x18004c7f7  mov     [r11+18h], rsi
0x18004c7fb  push    rdi
0x18004c7fc  sub     rsp, 40h
0x18004c800  mov     rcx, [rdx+38h]; hClientHandle
0x18004c804  mov     rdi, rdx
0x18004c807  mov     qword ptr [r11+20h], 0
0x18004c80f  test    rcx, rcx
0x18004c812  jz      loc_18004C935
0x18004c818  lea     rax, [r11+20h]
0x18004c81c  mov     qword ptr [r11-18h], 0
0x18004c824  mov     [r11-20h], rax
0x18004c828  xor     r9d, r9d; pReserved
0x18004c82b  lea     rax, [r11+10h]
0x18004c82f  mov     [rsp+48h+arg_8], 0
0x18004c837  add     rdx, 40h ; '@'; pInterfaceGuid
0x18004c83b  mov     [r11-28h], rax
0x18004c83f  lea     r8d, [r9+7]; OpCode
0x18004c843  call    cs:__imp_WlanQueryInterface
0x18004c849  test    eax, eax
0x18004c84b  jnz     loc_18004C908
0x18004c851  mov     rax, [rsp+48h+pMemory]
0x18004c856  xor     ecx, ecx
0x18004c858  mov     [rax+206h], cx
0x18004c85f  mov     rbx, [rsp+48h+pMemory]
0x18004c864  cmp     dword ptr [rbx+4], 1
0x18004c868  jnz     loc_18004C90D
0x18004c86e  lea     rcx, [rbx+8]; String1
0x18004c872  lea     rdx, aWcnTemporaryPr; "WCN Temporary Profile"
0x18004c879  call    wcscmp_0
0x18004c87e  test    eax, eax
0x18004c880  jnz     loc_18004C90D
0x18004c886  mov     eax, [rdi+50h]
0x18004c889  cmp     [rbx+208h], eax
0x18004c88f  jnz     short loc_18004C90D
0x18004c891  mov     r8d, eax; Size
0x18004c894  lea     rdx, [rdi+54h]; Buf2
0x18004c898  lea     rcx, [rbx+20Ch]; Buf1
0x18004c89f  call    memcmp_0
0x18004c8a4  test    eax, eax
0x18004c8a6  jnz     short loc_18004C90D
0x18004c8a8  mov     rcx, [rdi+38h]; hClientHandle
0x18004c8ac  lea     rdx, [rdi+40h]; pInterfaceGuid
0x18004c8b0  xor     r8d, r8d; pReserved
0x18004c8b3  call    cs:__imp_WlanDisconnect
0x18004c8b9  test    eax, eax
0x18004c8bb  jz      short loc_18004C908
0x18004c8bd  jg      short loc_18004C8C3
0x18004c8bf  mov     ecx, eax
0x18004c8c1  jmp     short loc_18004C8CC
0x18004c8c3  movzx   ecx, ax
0x18004c8c6  or      ecx, 80070000h
0x18004c8cc  mov     r10, cs:WPP_GLOBAL_Control
0x18004c8d3  lea     rdx, WPP_GLOBAL_Control
0x18004c8da  cmp     r10, rdx
0x18004c8dd  jz      short loc_18004C908
0x18004c8df  cmp     byte ptr [r10+19h], 3
0x18004c8e4  jb      short loc_18004C908
0x18004c8e6  or      ecx, 80000000h
0x18004c8ec  lea     r8, WPP_16f86085a523394303ca33111ba71bc3_Traceguids
0x18004c8f3  mov     [rsp+48h+var_28], ecx
0x18004c8f7  mov     edx, 2Eh ; '.'
0x18004c8fc  mov     rcx, [r10+10h]
0x18004c900  mov     r9d, eax
0x18004c903  call    WPP_SF_Dd
0x18004c908  mov     rbx, [rsp+48h+pMemory]
0x18004c90d  test    rbx, rbx
0x18004c910  jz      short loc_18004C91B
0x18004c912  mov     rcx, rbx; pMemory
0x18004c915  call    cs:__imp_WlanFreeMemory
0x18004c91b  mov     rcx, [rdi+38h]; hClientHandle
0x18004c91f  call    ?WcnWlanCloseHandle@@YAJPEAX@Z; WcnWlanCloseHandle(void *)
0x18004c924  mov     rcx, [rdi+10h]; this
0x18004c928  mov     qword ptr [rdi+38h], 0
0x18004c930  call    ?FinishDisconnect@CWcnSession@@QEAAXXZ; CWcnSession::FinishDisconnect(void)
0x18004c935  mov     rbx, [rsp+48h+arg_0]
0x18004c93a  mov     rsi, [rsp+48h+arg_10]
0x18004c93f  add     rsp, 40h
0x18004c943  pop     rdi
0x18004c944  retn
```
