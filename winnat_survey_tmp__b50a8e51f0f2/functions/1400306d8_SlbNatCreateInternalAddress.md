# SlbNatCreateInternalAddress

- ea: `0x1400306d8`
- end: `0x1400308a6`
- name: `SlbNatCreateInternalAddress`
- size: `462`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140033cc8`

## callees

- `0x14000820c`
- `0x14000caa0`
- `0x14000d678`
- `0x140013fbc`
- `0x14001ede0`
- `0x14002d008`
- `0x14002e220`
- `0x14002e324`
- `0x1400306d8`
- `0x140033204`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140030736`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030736`
- `ntoskrnl!ExAllocatePool2` at `0x1400307a9`
- `ntoskrnl!ExAllocatePool2` at `0x1400307a9`

## string_xrefs

- `0x14003071b`: `SlbNatCreateInternalAddress`

## pseudocode

```c
__int64 __fastcall SlbNatCreateInternalAddress(__int64 a1, __int16 a2, __int64 a3, NET_IFINDEX a4)
{
  unsigned int v7; // ebp
  IN6_ADDR *v8; // rbx
  __int64 Pool2; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  int v13; // r8d
  IN6_ADDR **v14; // rcx
  int v15; // [rsp+20h] [rbp-78h]
  _OWORD v16[2]; // [rsp+40h] [rbp-58h] BYREF

  if ( a2 != 2 )
  {
    v7 = -1073741637;
    v8 = 0;
    goto LABEL_3;
  }
  if ( (unsigned __int8)SlbNatIsInterfaceExternal(a4) && (BYTE8(xmmword_1400262D0) & 2) != 0 )
    WPP_SF_d(769, 38, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids, a4);
  Pool2 = ExAllocatePool2(256, 40, 1634291283);
  v8 = (IN6_ADDR *)Pool2;
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
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v12, v11);
  if ( (Microsoft_Windows_WinNatEnableBits & 0x10) != 0 )
  {
    memset(v16, 0, 28);
    INETADDR_SETSOCKADDR(2, (__int64)v16, v8 + 1, 0, 0);
    if ( dword_140026104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x10) != 0 )
      McTemplateK0zqbr1q_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
        (unsigned int)WINNATM_INTERNAL_ADDRESS_ADDITION,
        v13,
        a1 + 80,
        v15,
        (__int64)v16,
        *(_DWORD *)v8[2].u.Byte);
  }
  v14 = *(IN6_ADDR ***)(a1 + 56);
  if ( *v14 != (IN6_ADDR *)(a1 + 48) )
    __fastfail(3u);
  *(_QWORD *)v8->u.Byte = a1 + 48;
  *(_QWORD *)&v8->u.Word[4] = v14;
  *v14 = v8;
  *(_QWORD *)(a1 + 56) = v8;
  ++*(_DWORD *)(a1 + 64);
  return v7;
}

```

## disassembly

```asm
0x1400306d8  mov     [rsp+arg_8], rbx
0x1400306dd  mov     [rsp+arg_10], rbp
0x1400306e2  push    rsi
0x1400306e3  push    rdi
0x1400306e4  push    r12
0x1400306e6  push    r14
0x1400306e8  push    r15
0x1400306ea  sub     rsp, 70h
0x1400306ee  mov     rax, cs:__security_cookie
0x1400306f5  xor     rax, rsp
0x1400306f8  mov     [rsp+98h+var_38], rax
0x1400306fd  mov     r12d, 2
0x140030703  mov     r14d, r9d
0x140030706  mov     rbp, r8
0x140030709  mov     rsi, rcx
0x14003070c  cmp     dx, r12w
0x140030710  jz      short loc_14003076B
0x140030712  xor     edi, edi
0x140030714  mov     ebp, 0C00000BBh
0x140030719  mov     ebx, edi
0x14003071b  lea     r8, aSlbnatcreatein; "SlbNatCreateInternalAddress"
0x140030722  mov     edx, ebp
0x140030724  mov     ecx, r14d
0x140030727  call    SlbNatInsertErrorEntry
0x14003072c  test    rbx, rbx
0x14003072f  jz      short loc_140030742
0x140030731  xor     edx, edx; Tag
0x140030733  mov     rcx, rbx; P
0x140030736  call    cs:__imp_ExFreePoolWithTag
0x14003073d  nop     dword ptr [rax+rax+00h]
0x140030742  mov     eax, ebp
0x140030744  mov     rcx, [rsp+98h+var_38]
0x140030749  xor     rcx, rsp; StackCookie
0x14003074c  call    __security_check_cookie
0x140030751  lea     r11, [rsp+98h+var_28]
0x140030756  mov     rbx, [r11+38h]
0x14003075a  mov     rbp, [r11+40h]
0x14003075e  mov     rsp, r11
0x140030761  pop     r15
0x140030763  pop     r14
0x140030765  pop     r12
0x140030767  pop     rdi
0x140030768  pop     rsi
0x140030769  retn
0x14003076b  mov     ecx, r14d
0x14003076e  call    SlbNatIsInterfaceExternal
0x140030773  xor     edi, edi
0x140030775  test    al, al
0x140030777  jz      short loc_140030799
0x140030779  test    byte ptr cs:xmmword_1400262D0+8, r12b
0x140030780  jz      short loc_140030799
0x140030782  lea     edx, [rdi+26h]
0x140030785  mov     ecx, 301h
0x14003078a  mov     r9d, r14d
0x14003078d  lea     r8, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids
0x140030794  call    WPP_SF_d
0x140030799  mov     edx, 28h ; '('
0x14003079e  mov     ecx, 100h
0x1400307a3  mov     r8d, 61694E53h
0x1400307a9  call    cs:__imp_ExAllocatePool2
0x1400307b0  nop     dword ptr [rax+rax+00h]
0x1400307b5  mov     rbx, rax
0x1400307b8  test    rax, rax
0x1400307bb  jnz     short loc_1400307C7
0x1400307bd  mov     ebp, 0C000009Ah
0x1400307c2  jmp     loc_14003071B
0x1400307c7  mov     eax, [rbp+8]
0x1400307ca  mov     rdx, rsi
0x1400307cd  mov     [rbx+10h], eax
0x1400307d0  mov     ecx, r14d; InterfaceIndex
0x1400307d3  mov     [rbx+20h], r14d
0x1400307d7  mov     eax, [rsi+0F8h]
0x1400307dd  mov     r9, [rsi+10h]
0x1400307e1  mov     r8d, [rsi+44h]
0x1400307e5  mov     [rsp+98h+var_68], eax; int
0x1400307e9  mov     [rsp+98h+var_70], dil; char
0x1400307ee  mov     [rsp+98h+var_78], dil; char
0x1400307f3  call    SlbNatIpsAddInterfaceMapping
0x1400307f8  mov     ebp, eax
0x1400307fa  test    eax, eax
0x1400307fc  js      loc_14003071B
0x140030802  mov     ecx, r14d
0x140030805  call    SlbNatIsInterfaceInternal
0x14003080a  test    al, al
0x14003080c  jnz     short loc_140030813
0x14003080e  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140030813  test    cs:Microsoft_Windows_WinNatEnableBits, 10h
0x14003081a  jz      short loc_14003087C
0x14003081c  xorps   xmm0, xmm0
0x14003081f  mov     word ptr [rsp+98h+var_78], di
0x140030824  movups  [rsp+98h+var_58], xmm0
0x140030829  mov     ecx, r12d
0x14003082c  lea     r8, [rbx+10h]
0x140030830  mov     r9d, edi
0x140030833  lea     rdx, [rsp+98h+var_58]
0x140030838  movups  [rsp+98h+var_58+0Ch], xmm0
0x14003083d  call    INETADDR_SETSOCKADDR
0x140030842  cmp     cs:dword_140026104, 1
0x140030849  jnz     short loc_14003087C
0x14003084b  test    cs:Microsoft_Windows_WinNatEnableBits, 10h
0x140030852  jz      short loc_14003087C
0x140030854  mov     eax, [rbx+20h]
0x140030857  lea     r9, [rsi+50h]
0x14003085b  mov     [rsp+98h+var_68], eax
0x14003085f  lea     rdx, WINNATM_INTERNAL_ADDRESS_ADDITION
0x140030866  lea     rax, [rsp+98h+var_58]
0x14003086b  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x140030872  mov     qword ptr [rsp+98h+var_70], rax
0x140030877  call    McTemplateK0zqbr1q_EtwWriteTransfer
0x14003087c  lea     rax, [rsi+30h]
0x140030880  mov     rcx, [rax+8]
0x140030884  cmp     [rcx], rax
0x140030887  jz      short loc_140030890
0x140030889  mov     ecx, 3
0x14003088e  int     29h; Win8: RtlFailFast(ecx)
0x140030890  mov     [rbx], rax
0x140030893  mov     [rbx+8], rcx
0x140030897  mov     [rcx], rbx
0x14003089a  mov     [rax+8], rbx
0x14003089e  inc     dword ptr [rsi+40h]
0x1400308a1  jmp     loc_140030742
```
