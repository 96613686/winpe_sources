# PnpSetObjectProp

- ea: `0x180008220`
- end: `0x18000839d`
- name: `PnpSetObjectProp`
- size: `381`
- prototype: `__int64 __fastcall(DEVINSTID_W pDeviceID, __int64, __int64, const DEVPROPKEY *, DEVPROPTYPE PropertyType, PBYTE PropertyBuffer, ULONG PropertyBufferSize)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800056d0`
- `0x1800083b0`
- `0x180009ab0`

## callees

- `0x180008220`
- `0x1800117d4`
- `0x180013d90`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x18000829b`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x18000829b`
- `api-ms-win-devices-config-l1-1-1!CM_Set_DevNode_PropertyW` at `0x1800082cd`
- `api-ms-win-devices-config-l1-1-1!CM_Set_DevNode_PropertyW` at `0x1800082cd`

## pseudocode

```c
__int64 __fastcall PnpSetObjectProp(
        DEVINSTID_W pDeviceID,
        __int64 a2,
        __int64 a3,
        const DEVPROPKEY *a4,
        DEVPROPTYPE PropertyType,
        PBYTE PropertyBuffer,
        ULONG PropertyBufferSize)
{
  char *v9; // rcx
  CONFIGRET DevNodeW; // edi
  _QWORD *v11; // rcx
  DEVNODE pdnDevInst[3]; // [rsp+34h] [rbp-44h] BYREF
  __int128 v14; // [rsp+40h] [rbp-38h]
  __int128 v15; // [rsp+50h] [rbp-28h]

  pdnDevInst[0] = 0;
  v14 = 0;
  v15 = 0;
  v9 = (char *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_cdd22764e23f3ef2f313648d2298ffdc_Traceguids);
      v9 = (char *)WPP_GLOBAL_Control;
    }
    if ( v9 != (char *)&WPP_GLOBAL_Control && v9[28] < 0 )
      WPP_SF_(*((_QWORD *)v9 + 2), 13, WPP_cdd22764e23f3ef2f313648d2298ffdc_Traceguids);
  }
  DevNodeW = CM_Locate_DevNodeW(pdnDevInst, pDeviceID, 5u);
  if ( !DevNodeW )
    DevNodeW = CM_Set_DevNode_PropertyW(pdnDevInst[0], a4, PropertyType, PropertyBuffer, PropertyBufferSize, 0);
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_cdd22764e23f3ef2f313648d2298ffdc_Traceguids);
      v11 = WPP_GLOBAL_Control;
    }
    if ( v11 != &WPP_GLOBAL_Control && (*((_DWORD *)v11 + 7) & 0x10000000) != 0 )
      WPP_SF_(v11[2], 15, WPP_cdd22764e23f3ef2f313648d2298ffdc_Traceguids);
  }
  return DevNodeW;
}

```

## disassembly

```asm
0x180008220  mov     [rsp+arg_8], rbx
0x180008225  mov     [rsp+arg_10], rsi
0x18000822a  push    rdi
0x18000822b  push    r14
0x18000822d  push    r15
0x18000822f  sub     rsp, 60h
0x180008233  mov     rsi, r9
0x180008236  mov     rdi, rcx
0x180008239  mov     r14, [rsp+78h+PropertyBuffer]
0x180008241  xor     r15d, r15d
0x180008244  mov     [rsp+78h+var_48], r15d
0x180008249  mov     [rsp+78h+pdnDevInst], r15d
0x18000824e  xorps   xmm0, xmm0
0x180008251  movups  [rsp+78h+var_38], xmm0
0x180008256  xorps   xmm1, xmm1
0x180008259  movups  [rsp+78h+var_28], xmm1
0x18000825e  lea     rbx, WPP_GLOBAL_Control
0x180008265  mov     rcx, cs:WPP_GLOBAL_Control
0x18000826c  cmp     rcx, rbx
0x18000826f  jz      short loc_18000828D
0x180008271  test    dword ptr [rcx+1Ch], 10000000h
0x180008278  jnz     loc_18000832A
0x18000827e  cmp     rcx, rbx
0x180008281  jz      short loc_18000828D
0x180008283  test    byte ptr [rcx+1Ch], 80h
0x180008287  jnz     loc_18000834B
0x18000828d  mov     r8d, 5; ulFlags
0x180008293  mov     rdx, rdi; pDeviceID
0x180008296  lea     rcx, [rsp+78h+pdnDevInst]; pdnDevInst
0x18000829b  call    cs:__imp_CM_Locate_DevNodeW
0x1800082a1  mov     edi, eax
0x1800082a3  mov     [rsp+78h+var_48], eax
0x1800082a7  test    eax, eax
0x1800082a9  jnz     short loc_1800082D9
0x1800082ab  mov     [rsp+78h+ulFlags], r15d; ulFlags
0x1800082b0  mov     eax, [rsp+78h+arg_30]
0x1800082b7  mov     [rsp+78h+PropertyBufferSize], eax; PropertyBufferSize
0x1800082bb  mov     r9, r14; PropertyBuffer
0x1800082be  mov     r8d, [rsp+78h+PropertyType]; PropertyType
0x1800082c6  mov     rdx, rsi; PropertyKey
0x1800082c9  mov     ecx, [rsp+78h+pdnDevInst]; dnDevInst
0x1800082cd  call    cs:__imp_CM_Set_DevNode_PropertyW
0x1800082d3  mov     edi, eax
0x1800082d5  mov     [rsp+78h+var_48], eax
0x1800082d9  jmp     short loc_1800082F2
0x1800082db  mov     ecx, eax
0x1800082dd  lea     r8, [rsp+78h+var_48]
0x1800082e2  call    PnPExceptionHandler
0x1800082e7  lea     rbx, WPP_GLOBAL_Control
0x1800082ee  mov     edi, [rsp+78h+var_48]
0x1800082f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800082f9  cmp     rcx, rbx
0x1800082fc  jz      short loc_180008312
0x1800082fe  test    byte ptr [rcx+1Ch], 80h
0x180008302  jnz     short loc_180008365
0x180008304  cmp     rcx, rbx
0x180008307  jz      short loc_180008312
0x180008309  test    dword ptr [rcx+1Ch], 10000000h
0x180008310  jnz     short loc_180008383
0x180008312  mov     eax, edi
0x180008314  lea     r11, [rsp+78h+var_18]
0x180008319  mov     rbx, [r11+28h]
0x18000831d  mov     rsi, [r11+30h]
0x180008321  mov     rsp, r11
0x180008324  pop     r15
0x180008326  pop     r14
0x180008328  pop     rdi
0x180008329  retn
0x18000832a  mov     edx, 0Ch
0x18000832f  lea     r8, WPP_cdd22764e23f3ef2f313648d2298ffdc_Traceguids
0x180008336  mov     rcx, [rcx+10h]
0x18000833a  call    WPP_SF_
0x18000833f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008346  jmp     loc_18000827E
0x18000834b  mov     edx, 0Dh
0x180008350  lea     r8, WPP_cdd22764e23f3ef2f313648d2298ffdc_Traceguids
0x180008357  mov     rcx, [rcx+10h]
0x18000835b  call    WPP_SF_
0x180008360  jmp     loc_18000828D
0x180008365  mov     edx, 0Eh
0x18000836a  lea     r8, WPP_cdd22764e23f3ef2f313648d2298ffdc_Traceguids
0x180008371  mov     rcx, [rcx+10h]
0x180008375  call    WPP_SF_
0x18000837a  mov     rcx, cs:WPP_GLOBAL_Control
0x180008381  jmp     short loc_180008304
0x180008383  mov     edx, 0Fh
0x180008388  lea     r8, WPP_cdd22764e23f3ef2f313648d2298ffdc_Traceguids
0x18000838f  mov     rcx, [rcx+10h]
0x180008393  call    WPP_SF_
0x180008398  jmp     loc_180008312
0x180018ab0  push    rbp
0x180018ab2  sub     rsp, 30h
0x180018ab6  mov     rbp, rdx
0x180018ab9  mov     eax, 1
0x180018abe  add     rsp, 30h
0x180018ac2  pop     rbp
0x180018ac3  retn
```
