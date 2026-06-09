# VPNIKEProtocolEngine::ReleaseAllActiveConnections(void)

- ea: `0x180006698`
- end: `0x180006731`
- name: `?ReleaseAllActiveConnections@VPNIKEProtocolEngine@@QEAAXXZ`
- size: `153`
- prototype: `void __fastcall(VPNIKEProtocolEngine *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180057c30`

## callees

- `0x180006698`
- `0x180007794`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800066f3`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800066f3`

## pseudocode

```c
void __fastcall VPNIKEProtocolEngine::ReleaseAllActiveConnections(VPNIKEProtocolEngine *this)
{
  VPNIKEProtocolEngine *v1; // rbx
  PVOID *v2; // rcx

  v1 = VpnIkeProtocolEngine;
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 110, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)v1 + 17) )
  {
    SubmitThreadpoolWork(*((PTP_WORK *)v1 + 17));
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 6u )
    WPP_SF_(v2[2], 111, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids);
}

```

## disassembly

```asm
0x180006698  mov     [rsp+arg_0], rbx
0x18000669d  push    rdi
0x18000669e  sub     rsp, 20h
0x1800066a2  mov     rbx, cs:?VpnIkeProtocolEngine@@3PEAVVPNIKEProtocolEngine@@EA; VPNIKEProtocolEngine * VpnIkeProtocolEngine
0x1800066a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800066b0  lea     rdi, WPP_GLOBAL_Control
0x1800066b7  cmp     rcx, rdi
0x1800066ba  jz      short loc_1800066E4
0x1800066bc  test    byte ptr [rcx+1Ch], 1
0x1800066c0  jz      short loc_1800066E4
0x1800066c2  cmp     byte ptr [rcx+19h], 6
0x1800066c6  jb      short loc_1800066E4
0x1800066c8  mov     rcx, [rcx+10h]
0x1800066cc  lea     r8, WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids
0x1800066d3  mov     edx, 6Eh ; 'n'
0x1800066d8  call    WPP_SF_
0x1800066dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800066e4  mov     rax, [rbx+88h]
0x1800066eb  test    rax, rax
0x1800066ee  jz      short loc_180006700
0x1800066f0  mov     rcx, rax; pwk
0x1800066f3  call    cs:__imp_SubmitThreadpoolWork
0x1800066f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180006700  cmp     rcx, rdi
0x180006703  jz      short loc_180006726
0x180006705  test    byte ptr [rcx+1Ch], 1
0x180006709  jz      short loc_180006726
0x18000670b  cmp     byte ptr [rcx+19h], 6
0x18000670f  jb      short loc_180006726
0x180006711  mov     rcx, [rcx+10h]
0x180006715  lea     r8, WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids
0x18000671c  mov     edx, 6Fh ; 'o'
0x180006721  call    WPP_SF_
0x180006726  mov     rbx, [rsp+28h+arg_0]
0x18000672b  add     rsp, 20h
0x18000672f  pop     rdi
0x180006730  retn
```
