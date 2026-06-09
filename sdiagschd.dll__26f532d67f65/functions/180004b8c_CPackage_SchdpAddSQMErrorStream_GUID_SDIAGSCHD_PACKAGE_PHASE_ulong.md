# CPackage::SchdpAddSQMErrorStream(_GUID *,_SDIAGSCHD_PACKAGE_PHASE,ulong)

- ea: `0x180004b8c`
- end: `0x180004c3f`
- name: `?SchdpAddSQMErrorStream@CPackage@@AEAAJPEAU_GUID@@W4_SDIAGSCHD_PACKAGE_PHASE@@K@Z`
- size: `179`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180004340`
- `0x18000440c`
- `0x1800046ac`
- `0x1800048bc`
- `0x1800083d0`

## callees

- `0x180004b8c`
- `0x180004fd4`
- `0x18000b13c`
- `0x18000c860`

## import_xrefs

- `ntdll!WinSqmAddToStream` at `0x180004c13`
- `ntdll!WinSqmAddToStream` at `0x180004c13`

## pseudocode

```c
__int64 __fastcall CPackage::SchdpAddSQMErrorStream(CPackage *a1, __int64 a2, int a3, int a4)
{
  int StringKey; // eax
  unsigned int v8; // ebx
  unsigned int v10; // [rsp+20h] [rbp-58h] BYREF
  _DWORD v11[12]; // [rsp+28h] [rbp-50h] BYREF

  v10 = 0;
  StringKey = CPackage::SchdpGetStringKey(a1, *(const unsigned __int16 **)a1, &v10);
  v8 = StringKey;
  if ( StringKey >= 0 )
  {
    v11[0] = 1;
    v11[4] = 1;
    v11[8] = 1;
    v11[2] = v10;
    v11[6] = a3;
    v11[10] = a4;
    WinSqmAddToStream(a2, 3882, 3, v11);
  }
  else
  {
    SdpDebugTrace(1u, L"CPackage::SchdpAddSQMErrorStream", 0x1EDu, StringKey);
  }
  return v8;
}

```

## disassembly

```asm
0x180004b8c  mov     [rsp+arg_10], rbx
0x180004b91  push    rbp
0x180004b92  push    rsi
0x180004b93  push    rdi
0x180004b94  sub     rsp, 60h
0x180004b98  mov     rax, cs:__security_cookie
0x180004b9f  xor     rax, rsp
0x180004ba2  mov     [rsp+78h+var_20], rax
0x180004ba7  and     [rsp+78h+var_58], 0
0x180004bac  mov     esi, r8d
0x180004baf  mov     rbp, rdx
0x180004bb2  lea     r8, [rsp+78h+var_58]; unsigned int *
0x180004bb7  mov     rdx, [rcx]; unsigned __int16 *
0x180004bba  mov     edi, r9d
0x180004bbd  call    ?SchdpGetStringKey@CPackage@@AEAAJPEBGPEAK@Z; CPackage::SchdpGetStringKey(ushort const *,ulong *)
0x180004bc2  mov     ebx, eax
0x180004bc4  mov     ecx, 1; Level
0x180004bc9  test    eax, eax
0x180004bcb  jns     short loc_180004BE4
0x180004bcd  mov     r9d, eax; int
0x180004bd0  lea     rdx, aCpackageSchdpa_0; "CPackage::SchdpAddSQMErrorStream"
0x180004bd7  mov     r8d, 1EDh; int
0x180004bdd  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180004be2  jmp     short loc_180004C1F
0x180004be4  mov     eax, [rsp+78h+var_58]
0x180004be8  lea     r9, [rsp+78h+var_50]
0x180004bed  mov     [rsp+78h+var_50], ecx
0x180004bf1  mov     edx, 0F2Ah
0x180004bf6  mov     [rsp+78h+var_40], ecx
0x180004bfa  mov     r8d, 3
0x180004c00  mov     [rsp+78h+var_30], ecx
0x180004c04  mov     rcx, rbp
0x180004c07  mov     [rsp+78h+var_48], eax
0x180004c0b  mov     [rsp+78h+var_38], esi
0x180004c0f  mov     [rsp+78h+var_28], edi
0x180004c13  call    cs:__imp_WinSqmAddToStream
0x180004c1a  nop     dword ptr [rax+rax+00h]
0x180004c1f  mov     eax, ebx
0x180004c21  mov     rcx, [rsp+78h+var_20]
0x180004c26  xor     rcx, rsp; StackCookie
0x180004c29  call    __security_check_cookie
0x180004c2e  mov     rbx, [rsp+78h+arg_10]
0x180004c36  add     rsp, 60h
0x180004c3a  pop     rdi
0x180004c3b  pop     rsi
0x180004c3c  pop     rbp
0x180004c3d  retn
```
