# CWcnEapTransport::DoDiscoveryInternal(_DOT11_SSID const *,bool)

- ea: `0x180044fb8`
- end: `0x1800450bc`
- name: `?DoDiscoveryInternal@CWcnEapTransport@@AEAAJPEBU_DOT11_SSID@@_N@Z`
- size: `260`
- prototype: `__int64 __fastcall(CWcnEapTransport *this, const struct _DOT11_SSID *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x180045200`
- `0x1800452e0`

## callees

- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x180044fb8`
- `0x1800450c4`
- `0x1800454a0`
- `0x180053004`

## import_xrefs

- `wlanapi!WlanFreeMemory` at `0x180045070`
- `wlanapi!WlanFreeMemory` at `0x180045070`

## pseudocode

```c
__int64 __fastcall CWcnEapTransport::DoDiscoveryInternal(CWcnEapTransport *this, const struct _DOT11_SSID *a2)
{
  const char *Indent; // rax
  __int64 v5; // r10
  int v6; // eax
  int v7; // ebx
  _BYTE *v8; // r10
  unsigned int v9; // eax
  __int64 v10; // r10
  PVOID pMemory; // [rsp+78h] [rbp+20h] BYREF

  pMemory = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v5 + 16), 28, WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids, Indent);
  }
  v6 = CWcnEapTransport::EnumWlanInterfaces(this, (PWLAN_INTERFACE_INFO_LIST *)&pMemory);
  v7 = v6;
  if ( v6 >= 0 )
  {
    CWcnEapTransport::DoDiscoveryInternalWithList(this, (const struct _WLAN_INTERFACE_INFO_LIST *)pMemory, a2, 1);
    goto LABEL_9;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids, (unsigned int)v6);
LABEL_9:
    v8 = WPP_GLOBAL_Control;
  }
  if ( pMemory )
  {
    WlanFreeMemory(pMemory);
    v8 = WPP_GLOBAL_Control;
  }
  if ( v8 != (_BYTE *)&WPP_GLOBAL_Control && (v7 < 0 || v8[25] >= 6u) )
  {
    v9 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v10 + 16), 30, (unsigned int)WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids, v9, v7);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180044fb8  push    rbx
0x180044fba  push    rbp
0x180044fbb  push    rsi
0x180044fbc  push    rdi
0x180044fbd  sub     rsp, 38h
0x180044fc1  mov     rsi, rdx
0x180044fc4  mov     [rsp+58h+pMemory], 0
0x180044fcd  mov     rdi, rcx
0x180044fd0  mov     r10, cs:WPP_GLOBAL_Control
0x180044fd7  lea     rbp, WPP_GLOBAL_Control
0x180044fde  cmp     r10, rbp
0x180044fe1  jz      short loc_18004500C
0x180044fe3  cmp     byte ptr [r10+19h], 6
0x180044fe8  jb      short loc_18004500C
0x180044fea  mov     ecx, 1; int
0x180044fef  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180044ff4  mov     rcx, [r10+10h]
0x180044ff8  lea     r8, WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids
0x180044fff  mov     edx, 1Ch
0x180045004  mov     r9, rax
0x180045007  call    WPP_SF_s
0x18004500c  lea     rdx, [rsp+58h+pMemory]; ppInterfaceList
0x180045011  mov     rcx, rdi; pCallbackContext
0x180045014  call    ?EnumWlanInterfaces@CWcnEapTransport@@AEAAJPEAPEAU_WLAN_INTERFACE_INFO_LIST@@@Z; CWcnEapTransport::EnumWlanInterfaces(_WLAN_INTERFACE_INFO_LIST * *)
0x180045019  mov     ebx, eax
0x18004501b  test    eax, eax
0x18004501d  jns     short loc_18004504C
0x18004501f  mov     r10, cs:WPP_GLOBAL_Control
0x180045026  cmp     r10, rbp
0x180045029  jz      short loc_180045066
0x18004502b  cmp     byte ptr [r10+19h], 2
0x180045030  jb      short loc_180045066
0x180045032  mov     rcx, [r10+10h]
0x180045036  lea     r8, WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids
0x18004503d  mov     edx, 1Dh
0x180045042  mov     r9d, eax
0x180045045  call    WPP_SF_d
0x18004504a  jmp     short loc_18004505F
0x18004504c  mov     rdx, [rsp+58h+pMemory]; struct _WLAN_INTERFACE_INFO_LIST *
0x180045051  mov     r9b, 1; bool
0x180045054  mov     r8, rsi; struct _DOT11_SSID *
0x180045057  mov     rcx, rdi; this
0x18004505a  call    ?DoDiscoveryInternalWithList@CWcnEapTransport@@AEAAXPEBU_WLAN_INTERFACE_INFO_LIST@@PEBU_DOT11_SSID@@_N@Z; CWcnEapTransport::DoDiscoveryInternalWithList(_WLAN_INTERFACE_INFO_LIST const *,_DOT11_SSID const *,bool)
0x18004505f  mov     r10, cs:WPP_GLOBAL_Control
0x180045066  mov     rcx, [rsp+58h+pMemory]; pMemory
0x18004506b  test    rcx, rcx
0x18004506e  jz      short loc_18004507D
0x180045070  call    cs:__imp_WlanFreeMemory
0x180045076  mov     r10, cs:WPP_GLOBAL_Control
0x18004507d  cmp     r10, rbp
0x180045080  jz      short loc_1800450B1
0x180045082  test    ebx, ebx
0x180045084  js      short loc_18004508D
0x180045086  cmp     byte ptr [r10+19h], 6
0x18004508b  jb      short loc_1800450B1
0x18004508d  or      ecx, 0FFFFFFFFh; int
0x180045090  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180045095  mov     rcx, [r10+10h]
0x180045099  lea     r8, WPP_2a2ab5d430b23a08e2857db812a1a249_Traceguids
0x1800450a0  mov     edx, 1Eh
0x1800450a5  mov     [rsp+58h+var_38], ebx
0x1800450a9  mov     r9, rax
0x1800450ac  call    WPP_SF_sd
0x1800450b1  mov     eax, ebx
0x1800450b3  add     rsp, 38h
0x1800450b7  pop     rdi
0x1800450b8  pop     rsi
0x1800450b9  pop     rbp
0x1800450ba  pop     rbx
0x1800450bb  retn
```
