# SlbNatCreateInternalAddress

- ea: `0x140031808`
- end: `0x1400319d6`
- name: `SlbNatCreateInternalAddress`
- size: `462`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140034fd8`

## callees

- `0x14000820c`
- `0x14000caa0`
- `0x14000d648`
- `0x1400148fc`
- `0x14001f320`
- `0x14002e008`
- `0x14002f220`
- `0x14002f324`
- `0x140031808`
- `0x140034334`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140031866`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031866`
- `ntoskrnl!ExAllocatePool2` at `0x1400318d9`
- `ntoskrnl!ExAllocatePool2` at `0x1400318d9`

## string_xrefs

- `0x14003184b`: `SlbNatCreateInternalAddress`

## pseudocode

```c
__int64 __fastcall SlbNatCreateInternalAddress(__int64 a1, __int16 a2, __int64 a3, NET_IFINDEX a4)
{
  unsigned int v7; // ebp
  _QWORD *v8; // rbx
  __int64 Pool2; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  int v14; // r8d
  _QWORD *v15; // rcx
  int v16; // [rsp+20h] [rbp-78h]
  _OWORD v17[2]; // [rsp+40h] [rbp-58h] BYREF

  if ( a2 != 2 )
  {
    v7 = -1073741637;
    v8 = 0;
    goto LABEL_3;
  }
  if ( (unsigned __int8)SlbNatIsInterfaceExternal(a4) && (BYTE8(xmmword_1400272D0) & 2) != 0 )
    WPP_SF_d(769, 38, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids, a4);
  Pool2 = ExAllocatePool2(256, 40, 1634291283);
  v8 = (_QWORD *)Pool2;
  if ( !Pool2 )
  {
    v7 = -1073741670;
    goto LABEL_3;
  }
  *(_DWORD *)(Pool2 + 16) = *(_DWORD *)(a3 + 8);
  *(_DWORD *)(Pool2 + 32) = a4;
  v7 = SlbNatIpsAddInterfaceMapping(a4, 0, 0, *(_DWORD *)(a1 + 248));
  if ( (v7 & 0x80000000) != 0 )
  {
LABEL_3:
    SlbNatInsertErrorEntry(a4, v7, L"SlbNatCreateInternalAddress");
    if ( v8 )
      ExFreePoolWithTag(v8, 0);
    return v7;
  }
  if ( !(unsigned __int8)SlbNatIsInterfaceInternal(a4) )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v12, v11, v13);
  if ( (Microsoft_Windows_WinNatEnableBits & 0x10) != 0 )
  {
    memset(v17, 0, 28);
    INETADDR_SETSOCKADDR(2, (unsigned int)v17, (_DWORD)v8 + 16, 0, 0);
    if ( dword_140027104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x10) != 0 )
      McTemplateK0zqbr1q_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
        (unsigned int)WINNATM_INTERNAL_ADDRESS_ADDITION,
        v14,
        a1 + 80,
        v16,
        (__int64)v17,
        *((_DWORD *)v8 + 8));
  }
  v15 = *(_QWORD **)(a1 + 56);
  if ( *v15 != a1 + 48 )
    __fastfail(3u);
  *v8 = a1 + 48;
  v8[1] = v15;
  *v15 = v8;
  *(_QWORD *)(a1 + 56) = v8;
  ++*(_DWORD *)(a1 + 64);
  return v7;
}

```

## disassembly

```asm
0x140031808  mov     [rsp+arg_8], rbx
0x14003180d  mov     [rsp+arg_10], rbp
0x140031812  push    rsi
0x140031813  push    rdi
0x140031814  push    r12
0x140031816  push    r14
0x140031818  push    r15
0x14003181a  sub     rsp, 70h
0x14003181e  mov     rax, cs:__security_cookie
0x140031825  xor     rax, rsp
0x140031828  mov     [rsp+98h+var_38], rax
0x14003182d  mov     r12d, 2
0x140031833  mov     r14d, r9d
0x140031836  mov     rbp, r8
0x140031839  mov     rsi, rcx
0x14003183c  cmp     dx, r12w
0x140031840  jz      short loc_14003189B
0x140031842  xor     edi, edi
0x140031844  mov     ebp, 0C00000BBh
0x140031849  mov     ebx, edi
0x14003184b  lea     r8, aSlbnatcreatein; "SlbNatCreateInternalAddress"
0x140031852  mov     edx, ebp
0x140031854  mov     ecx, r14d
0x140031857  call    SlbNatInsertErrorEntry
0x14003185c  test    rbx, rbx
0x14003185f  jz      short loc_140031872
0x140031861  xor     edx, edx; Tag
0x140031863  mov     rcx, rbx; P
0x140031866  call    cs:__imp_ExFreePoolWithTag
0x14003186d  nop     dword ptr [rax+rax+00h]
0x140031872  mov     eax, ebp
0x140031874  mov     rcx, [rsp+98h+var_38]
0x140031879  xor     rcx, rsp; StackCookie
0x14003187c  call    __security_check_cookie
0x140031881  lea     r11, [rsp+98h+var_28]
0x140031886  mov     rbx, [r11+38h]
0x14003188a  mov     rbp, [r11+40h]
0x14003188e  mov     rsp, r11
0x140031891  pop     r15
0x140031893  pop     r14
0x140031895  pop     r12
0x140031897  pop     rdi
0x140031898  pop     rsi
0x140031899  retn
0x14003189b  mov     ecx, r14d
0x14003189e  call    SlbNatIsInterfaceExternal
0x1400318a3  xor     edi, edi
0x1400318a5  test    al, al
0x1400318a7  jz      short loc_1400318C9
0x1400318a9  test    byte ptr cs:xmmword_1400272D0+8, r12b
0x1400318b0  jz      short loc_1400318C9
0x1400318b2  lea     edx, [rdi+26h]
0x1400318b5  mov     ecx, 301h
0x1400318ba  mov     r9d, r14d
0x1400318bd  lea     r8, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids
0x1400318c4  call    WPP_SF_d
0x1400318c9  mov     edx, 28h ; '('
0x1400318ce  mov     ecx, 100h
0x1400318d3  mov     r8d, 61694E53h
0x1400318d9  call    cs:__imp_ExAllocatePool2
0x1400318e0  nop     dword ptr [rax+rax+00h]
0x1400318e5  mov     rbx, rax
0x1400318e8  test    rax, rax
0x1400318eb  jnz     short loc_1400318F7
0x1400318ed  mov     ebp, 0C000009Ah
0x1400318f2  jmp     loc_14003184B
0x1400318f7  mov     eax, [rbp+8]
0x1400318fa  mov     rdx, rsi
0x1400318fd  mov     [rbx+10h], eax
0x140031900  mov     ecx, r14d; InterfaceIndex
0x140031903  mov     [rbx+20h], r14d
0x140031907  mov     eax, [rsi+0F8h]
0x14003190d  mov     r9, [rsi+10h]
0x140031911  mov     r8d, [rsi+44h]
0x140031915  mov     [rsp+98h+var_68], eax; int
0x140031919  mov     [rsp+98h+var_70], dil; char
0x14003191e  mov     [rsp+98h+var_78], dil; char
0x140031923  call    SlbNatIpsAddInterfaceMapping
0x140031928  mov     ebp, eax
0x14003192a  test    eax, eax
0x14003192c  js      loc_14003184B
0x140031932  mov     ecx, r14d
0x140031935  call    SlbNatIsInterfaceInternal
0x14003193a  test    al, al
0x14003193c  jnz     short loc_140031943
0x14003193e  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140031943  test    cs:Microsoft_Windows_WinNatEnableBits, 10h
0x14003194a  jz      short loc_1400319AC
0x14003194c  xorps   xmm0, xmm0
0x14003194f  mov     word ptr [rsp+98h+var_78], di
0x140031954  movups  [rsp+98h+var_58], xmm0
0x140031959  mov     ecx, r12d
0x14003195c  lea     r8, [rbx+10h]
0x140031960  mov     r9d, edi
0x140031963  lea     rdx, [rsp+98h+var_58]
0x140031968  movups  [rsp+98h+var_58+0Ch], xmm0
0x14003196d  call    INETADDR_SETSOCKADDR
0x140031972  cmp     cs:dword_140027104, 1
0x140031979  jnz     short loc_1400319AC
0x14003197b  test    cs:Microsoft_Windows_WinNatEnableBits, 10h
0x140031982  jz      short loc_1400319AC
0x140031984  mov     eax, [rbx+20h]
0x140031987  lea     r9, [rsi+50h]
0x14003198b  mov     [rsp+98h+var_68], eax
0x14003198f  lea     rdx, WINNATM_INTERNAL_ADDRESS_ADDITION
0x140031996  lea     rax, [rsp+98h+var_58]
0x14003199b  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x1400319a2  mov     qword ptr [rsp+98h+var_70], rax
0x1400319a7  call    McTemplateK0zqbr1q_EtwWriteTransfer
0x1400319ac  lea     rax, [rsi+30h]
0x1400319b0  mov     rcx, [rax+8]
0x1400319b4  cmp     [rcx], rax
0x1400319b7  jz      short loc_1400319C0
0x1400319b9  mov     ecx, 3
0x1400319be  int     29h; Win8: RtlFailFast(ecx)
0x1400319c0  mov     [rbx], rax
0x1400319c3  mov     [rbx+8], rcx
0x1400319c7  mov     [rcx], rbx
0x1400319ca  mov     [rax+8], rbx
0x1400319ce  inc     dword ptr [rsi+40h]
0x1400319d1  jmp     loc_140031872
```
