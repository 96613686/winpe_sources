# ParentFindAltConfiguration

- ea: `0x140022ee4`
- end: `0x140022fe0`
- name: `ParentFindAltConfiguration`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140028f7c`

## callees

- `0x14000a6cc`
- `0x140022ee4`
- `0x14002e100`

## string_xrefs

- `0x140022f27`: `AltConfigurationValue`

## pseudocode

```c
__int64 __fastcall ParentFindAltConfiguration(__int64 a1, _BYTE *a2)
{
  struct _DEVICE_OBJECT *v4; // rcx
  int PdoRegistryParameter; // eax
  int v6; // edx
  unsigned int v7; // ebx
  ULONG v9; // [rsp+30h] [rbp-18h]
  int v10; // [rsp+50h] [rbp+8h] BYREF
  int v11; // [rsp+60h] [rbp+18h] BYREF

  LOBYTE(v9) = 0;
  v4 = *(struct _DEVICE_OBJECT **)(a1 + 24);
  v11 = 0;
  v10 = 0;
  PdoRegistryParameter = GetPdoRegistryParameter(v4, L"AltConfigurationValue", &v10, 4u, &v11, 0, v9);
  v7 = PdoRegistryParameter;
  if ( PdoRegistryParameter >= 0 )
  {
    if ( v11 != 4 || (_BYTE)v10 == *a2 || (unsigned __int8)v10 >= *(_BYTE *)(a1 + 113) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v6) = 2;
        WPP_RECORDER_SF_d(
          *(_QWORD *)(a1 + 1368),
          v6,
          8,
          70,
          (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids,
          v10);
      }
      return (unsigned int)-1073741811;
    }
    else
    {
      *a2 = v10;
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v6) = 2;
    WPP_RECORDER_SF_d(
      *(_QWORD *)(a1 + 1368),
      v6,
      1,
      69,
      (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids,
      PdoRegistryParameter);
  }
  return v7;
}

```

## disassembly

```asm
0x140022ee4  mov     rax, rsp
0x140022ee7  mov     [rax+10h], rbx
0x140022eeb  mov     [rax+20h], rsi
0x140022eef  push    rdi
0x140022ef0  sub     rsp, 40h
0x140022ef4  mov     byte ptr [rax-18h], 0
0x140022ef8  mov     rsi, rdx
0x140022efb  mov     qword ptr [rax-20h], 0
0x140022f03  mov     rdi, rcx
0x140022f06  mov     rcx, [rcx+18h]
0x140022f0a  mov     r9d, 4
0x140022f10  mov     dword ptr [rax+18h], 0
0x140022f17  lea     r8, [rsp+48h+arg_0]
0x140022f1c  mov     dword ptr [rax+8], 0
0x140022f23  lea     rax, [rax+18h]
0x140022f27  lea     rdx, aAltconfigurati; "AltConfigurationValue"
0x140022f2e  mov     [rsp+48h+var_28], rax
0x140022f33  call    GetPdoRegistryParameter
0x140022f38  mov     ebx, eax
0x140022f3a  test    eax, eax
0x140022f3c  jns     short loc_140022F78
0x140022f3e  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140022f45  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140022f4c  jz      short loc_140022FCD
0x140022f4e  mov     rcx, [rdi+558h]
0x140022f55  mov     r9d, 45h ; 'E'
0x140022f5b  mov     [rsp+48h+var_20], eax
0x140022f5f  mov     dl, 2
0x140022f61  lea     rax, WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids
0x140022f68  mov     [rsp+48h+var_28], rax
0x140022f6d  lea     r8d, [r9-44h]
0x140022f71  call    WPP_RECORDER_SF_d
0x140022f76  jmp     short loc_140022FCD
0x140022f78  cmp     [rsp+48h+arg_10], 4
0x140022f7d  mov     eax, [rsp+48h+arg_0]
0x140022f81  jnz     short loc_140022F90
0x140022f83  cmp     al, [rsi]
0x140022f85  jz      short loc_140022F90
0x140022f87  cmp     al, [rdi+71h]
0x140022f8a  jnb     short loc_140022F90
0x140022f8c  mov     [rsi], al
0x140022f8e  jmp     short loc_140022FCD
0x140022f90  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140022f97  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140022f9e  jz      short loc_140022FC8
0x140022fa0  mov     rcx, [rdi+558h]
0x140022fa7  mov     r9d, 46h ; 'F'
0x140022fad  mov     [rsp+48h+var_20], eax
0x140022fb1  mov     dl, 2
0x140022fb3  lea     rax, WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids
0x140022fba  mov     [rsp+48h+var_28], rax
0x140022fbf  lea     r8d, [r9-3Eh]
0x140022fc3  call    WPP_RECORDER_SF_d
0x140022fc8  mov     ebx, 0C000000Dh
0x140022fcd  mov     rsi, [rsp+48h+arg_18]
0x140022fd2  mov     eax, ebx
0x140022fd4  mov     rbx, [rsp+48h+arg_8]
0x140022fd9  add     rsp, 40h
0x140022fdd  pop     rdi
0x140022fde  retn
```
