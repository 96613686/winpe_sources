# CWdsDeviceControllerPacket::AddManagementControllerList(CDynArray<ushort *,CDeallocateString> *)

- ea: `0x18000dbf4`
- end: `0x18000dce6`
- name: `?AddManagementControllerList@CWdsDeviceControllerPacket@@QEAAKPEAV?$CDynArray@PEAGVCDeallocateString@@@@@Z`
- size: `242`
- prototype: `__int64 __fastcall(CControlPacket *this, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180002bd8`

## callees

- `0x18000dbf4`
- `0x18001284c`
- `0x180012910`
- `0x180014d58`

## string_xrefs

- `0x18000dc36`: `base\eco\wds\lib\metadata\com\wdsdevicecontrollerpacket.cpp`
- `0x18000dc71`: `base\eco\wds\lib\metadata\com\wdsdevicecontrollerpacket.cpp`
- `0x18000dca7`: `base\eco\wds\lib\metadata\com\wdsdevicecontrollerpacket.cpp`

## pseudocode

```c
__int64 __fastcall CWdsDeviceControllerPacket::AddManagementControllerList(
        CControlPacket *this,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  unsigned int v4; // ebp
  unsigned int v7; // ebx
  const char *v8; // rdx
  const char *v9; // rdx
  unsigned int v10; // edi
  __int64 v11; // rsi
  unsigned __int16 *v12; // r15
  const char *v13; // rdx

  v4 = *(_DWORD *)(a2 + 12);
  v7 = CControlPacket::AddULONG(this, L"ControllerList", L"Count", a4, v4);
  if ( !ElValidateWin32(v7, v8, "base\\eco\\wds\\lib\\metadata\\com\\wdsdevicecontrollerpacket.cpp", 0xAAu) )
  {
    v10 = 0;
    if ( v4 )
    {
      v11 = 0;
      do
      {
        v12 = 0;
        v7 = 0;
        if ( v10 < *(_DWORD *)(a2 + 12) )
          v12 = *(unsigned __int16 **)(v11 + *(_QWORD *)a2);
        else
          v7 = 1413;
        if ( ElValidateWin32(v7, v9, "base\\eco\\wds\\lib\\metadata\\com\\wdsdevicecontrollerpacket.cpp", 0xB1u) )
          break;
        v7 = CControlPacket::AddString(this, (const char *)L"ControllerList", L"Entry", v10, v12);
        if ( ElValidateWin32(v7, v13, "base\\eco\\wds\\lib\\metadata\\com\\wdsdevicecontrollerpacket.cpp", 0xB7u) )
          break;
        ++v10;
        v11 += 8;
      }
      while ( v10 < v4 );
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18000dbf4  mov     rax, rsp
0x18000dbf7  mov     [rax+8], rbx
0x18000dbfb  mov     [rax+10h], rbp
0x18000dbff  mov     [rax+18h], rsi
0x18000dc03  mov     [rax+20h], rdi
0x18000dc07  push    r12
0x18000dc09  push    r14
0x18000dc0b  push    r15
0x18000dc0d  sub     rsp, 30h
0x18000dc11  mov     ebp, [rdx+0Ch]
0x18000dc14  lea     r8, aCount
0x18000dc1b  mov     r14, rdx
0x18000dc1e  mov     [rax-28h], ebp
0x18000dc21  lea     rdx, aControllerlist
0x18000dc28  mov     r12, rcx
0x18000dc2b  call    ?AddULONG@CControlPacket@@QEAAKPEBG0KK@Z
0x18000dc30  mov     r9d, 0AAh; unsigned int
0x18000dc36  lea     r8, aBaseEcoWdsLibM_5
0x18000dc3d  mov     ecx, eax; unsigned int
0x18000dc3f  mov     ebx, eax
0x18000dc41  call    ?ElValidateWin32@@YAKKPEBD0K@Z
0x18000dc46  test    eax, eax
0x18000dc48  jnz     short loc_18000DCC5
0x18000dc4a  xor     edi, edi
0x18000dc4c  test    ebp, ebp
0x18000dc4e  jz      short loc_18000DCC5
0x18000dc50  xor     esi, esi
0x18000dc52  xor     r15d, r15d
0x18000dc55  xor     ebx, ebx
0x18000dc57  cmp     edi, [r14+0Ch]
0x18000dc5b  jb      short loc_18000DC64
0x18000dc5d  mov     ebx, 585h
0x18000dc62  jmp     short loc_18000DC6B
0x18000dc64  mov     rax, [r14]
0x18000dc67  mov     r15, [rsi+rax]
0x18000dc6b  mov     r9d, 0B1h; unsigned int
0x18000dc71  lea     r8, aBaseEcoWdsLibM_5
0x18000dc78  mov     ecx, ebx; unsigned int
0x18000dc7a  call    ?ElValidateWin32@@YAKKPEBD0K@Z
0x18000dc7f  test    eax, eax
0x18000dc81  jnz     short loc_18000DCC5
0x18000dc83  mov     r9d, edi; unsigned int
0x18000dc86  mov     [rsp+48h+var_28], r15; unsigned __int16 *
0x18000dc8b  lea     r8, aEntry
0x18000dc92  mov     rcx, r12; this
0x18000dc95  lea     rdx, aControllerlist
0x18000dc9c  call    ?AddString@CControlPacket@@QEAAKPEBG0K0@Z
0x18000dca1  mov     r9d, 0B7h; unsigned int
0x18000dca7  lea     r8, aBaseEcoWdsLibM_5
0x18000dcae  mov     ecx, eax; unsigned int
0x18000dcb0  mov     ebx, eax
0x18000dcb2  call    ?ElValidateWin32@@YAKKPEBD0K@Z
0x18000dcb7  test    eax, eax
0x18000dcb9  jnz     short loc_18000DCC5
0x18000dcbb  inc     edi
0x18000dcbd  add     rsi, 8
0x18000dcc1  cmp     edi, ebp
0x18000dcc3  jb      short loc_18000DC52
0x18000dcc5  mov     rbp, [rsp+48h+arg_8]
0x18000dcca  mov     eax, ebx
0x18000dccc  mov     rbx, [rsp+48h+arg_0]
0x18000dcd1  mov     rsi, [rsp+48h+arg_10]
0x18000dcd6  mov     rdi, [rsp+48h+arg_18]
0x18000dcdb  add     rsp, 30h
0x18000dcdf  pop     r15
0x18000dce1  pop     r14
0x18000dce3  pop     r12
0x18000dce5  retn
```
