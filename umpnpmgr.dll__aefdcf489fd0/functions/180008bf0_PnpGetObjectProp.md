# PnpGetObjectProp

- ea: `0x180008bf0`
- end: `0x180008d18`
- name: `PnpGetObjectProp`
- size: `296`
- prototype: `__int64 __fastcall(DEVINSTID_W pDeviceID, __int64, __int64, const DEVPROPKEY *, DEVPROPTYPE *PropertyType, PBYTE PropertyBuffer, PULONG PropertyBufferSize)`
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800083b0`
- `0x180008660`
- `0x1800086c0`
- `0x180009690`
- `0x180009ab0`
- `0x180009bc4`

## callees

- `0x180008bf0`
- `0x1800117d4`
- `0x180013d90`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x180008c6d`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x180008c6d`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x180008c94`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x180008c94`

## pseudocode

```c
__int64 __fastcall PnpGetObjectProp(
        DEVINSTID_W pDeviceID,
        __int64 a2,
        __int64 a3,
        const DEVPROPKEY *a4,
        DEVPROPTYPE *PropertyType,
        PBYTE PropertyBuffer,
        PULONG PropertyBufferSize)
{
  CONFIGRET DevNodeW; // ebx
  DEVNODE pdnDevInst[3]; // [rsp+34h] [rbp-54h] BYREF
  __int128 v12; // [rsp+40h] [rbp-48h]
  __int128 v13; // [rsp+50h] [rbp-38h]

  pdnDevInst[0] = 0;
  v12 = 0;
  v13 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_cdd22764e23f3ef2f313648d2298ffdc_Traceguids);
  DevNodeW = CM_Locate_DevNodeW(pdnDevInst, pDeviceID, 5u);
  if ( !DevNodeW )
    DevNodeW = CM_Get_DevNode_PropertyW(pdnDevInst[0], a4, PropertyType, PropertyBuffer, PropertyBufferSize, 0);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_cdd22764e23f3ef2f313648d2298ffdc_Traceguids);
  return DevNodeW;
}

```

## disassembly

```asm
0x180008bf0  mov     [rsp+arg_8], rbx
0x180008bf5  mov     [rsp+arg_10], rsi
0x180008bfa  push    rdi
0x180008bfb  push    r12
0x180008bfd  push    r13
0x180008bff  push    r14
0x180008c01  push    r15
0x180008c03  sub     rsp, 60h
0x180008c07  mov     rsi, r9
0x180008c0a  mov     rbx, rcx
0x180008c0d  mov     r14, [rsp+88h+PropertyType]
0x180008c15  mov     r15, [rsp+88h+PropertyBuffer]
0x180008c1d  mov     r12, [rsp+88h+arg_30]
0x180008c25  xor     r13d, r13d
0x180008c28  mov     [rsp+88h+var_58], r13d
0x180008c2d  mov     [rsp+88h+pdnDevInst], r13d
0x180008c32  xorps   xmm0, xmm0
0x180008c35  movups  [rsp+88h+var_48], xmm0
0x180008c3a  xorps   xmm1, xmm1
0x180008c3d  movups  [rsp+88h+var_38], xmm1
0x180008c42  lea     rdi, WPP_GLOBAL_Control
0x180008c49  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c50  cmp     rcx, rdi
0x180008c53  jz      short loc_180008C5F
0x180008c55  test    byte ptr [rcx+1Ch], 80h
0x180008c59  jnz     loc_180008CE7
0x180008c5f  mov     r8d, 5; ulFlags
0x180008c65  mov     rdx, rbx; pDeviceID
0x180008c68  lea     rcx, [rsp+88h+pdnDevInst]; pdnDevInst
0x180008c6d  call    cs:__imp_CM_Locate_DevNodeW
0x180008c73  mov     ebx, eax
0x180008c75  mov     [rsp+88h+var_58], eax
0x180008c79  test    eax, eax
0x180008c7b  jnz     short loc_180008CA0
0x180008c7d  mov     [rsp+88h+ulFlags], r13d; ulFlags
0x180008c82  mov     [rsp+88h+PropertyBufferSize], r12; PropertyBufferSize
0x180008c87  mov     r9, r15; PropertyBuffer
0x180008c8a  mov     r8, r14; PropertyType
0x180008c8d  mov     rdx, rsi; PropertyKey
0x180008c90  mov     ecx, [rsp+88h+pdnDevInst]; dnDevInst
0x180008c94  call    cs:__imp_CM_Get_DevNode_PropertyW
0x180008c9a  mov     ebx, eax
0x180008c9c  mov     [rsp+88h+var_58], eax
0x180008ca0  jmp     short loc_180008CB9
0x180008ca2  mov     ecx, eax
0x180008ca4  lea     r8, [rsp+88h+var_58]
0x180008ca9  call    PnPExceptionHandler
0x180008cae  lea     rdi, WPP_GLOBAL_Control
0x180008cb5  mov     ebx, [rsp+88h+var_58]
0x180008cb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180008cc0  cmp     rcx, rdi
0x180008cc3  jz      short loc_180008CCB
0x180008cc5  test    byte ptr [rcx+1Ch], 80h
0x180008cc9  jnz     short loc_180008D01
0x180008ccb  mov     eax, ebx
0x180008ccd  lea     r11, [rsp+88h+var_28]
0x180008cd2  mov     rbx, [r11+38h]
0x180008cd6  mov     rsi, [r11+40h]
0x180008cda  mov     rsp, r11
0x180008cdd  pop     r15
0x180008cdf  pop     r14
0x180008ce1  pop     r13
0x180008ce3  pop     r12
0x180008ce5  pop     rdi
0x180008ce6  retn
0x180008ce7  mov     edx, 0Ah
0x180008cec  lea     r8, WPP_cdd22764e23f3ef2f313648d2298ffdc_Traceguids
0x180008cf3  mov     rcx, [rcx+10h]
0x180008cf7  call    WPP_SF_
0x180008cfc  jmp     loc_180008C5F
0x180008d01  mov     edx, 0Bh
0x180008d06  lea     r8, WPP_cdd22764e23f3ef2f313648d2298ffdc_Traceguids
0x180008d0d  mov     rcx, [rcx+10h]
0x180008d11  call    WPP_SF_
0x180008d16  jmp     short loc_180008CCB
0x180018b50  push    rbp
0x180018b52  sub     rsp, 30h
0x180018b56  mov     rbp, rdx
0x180018b59  mov     eax, 1
0x180018b5e  add     rsp, 30h
0x180018b62  pop     rbp
0x180018b63  retn
```
