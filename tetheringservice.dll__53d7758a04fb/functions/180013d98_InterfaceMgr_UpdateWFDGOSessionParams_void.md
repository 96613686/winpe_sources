# InterfaceMgr::UpdateWFDGOSessionParams(void)

- ea: `0x180013d98`
- end: `0x180013ed9`
- name: `?UpdateWFDGOSessionParams@InterfaceMgr@@AEAAJXZ`
- size: `321`
- prototype: `__int64 __fastcall(InterfaceMgr *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x1800110d4`

## callees

- `0x18000bf4c`
- `0x18000bf74`
- `0x180013d98`

## import_xrefs

- `wlanapi!WFDQueryPropertyInt` at `0x180013dfc`
- `wlanapi!WFDQueryPropertyInt` at `0x180013dfc`
- `wlanapi!WFDFreeMemoryInt` at `0x180013e97`
- `wlanapi!WFDFreeMemoryInt` at `0x180013e97`

## pseudocode

```c
__int64 __fastcall InterfaceMgr::UpdateWFDGOSessionParams(InterfaceMgr *this)
{
  __int64 v2; // rcx
  int v3; // eax
  unsigned int v4; // ebx
  TetheringServiceTelemetry *v5; // rcx
  __int64 v6; // rdx
  unsigned int v7; // ecx
  __int64 v8; // rax
  int v10; // [rsp+30h] [rbp+8h] BYREF
  __int64 v11; // [rsp+38h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, &WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids);
  }
  v2 = *((_QWORD *)this + 7);
  v10 = 0;
  v11 = 0;
  v3 = WFDQueryPropertyInt(v2, 4, &v10, &v11);
  v4 = v3;
  if ( v3 )
  {
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      v6 = v11;
      goto LABEL_17;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, &WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids, v4);
    v6 = v11;
  }
  else
  {
    v6 = v11;
    v7 = 0;
    v4 = -2147023728;
    if ( *(_DWORD *)(v11 + 4) )
    {
      while ( 1 )
      {
        v8 = 284LL * v7;
        if ( *(_DWORD *)(v8 + v11 + 12) == 2 )
          break;
        if ( ++v7 >= *(_DWORD *)(v11 + 4) )
          goto LABEL_16;
      }
      v4 = 0;
      *(_OWORD *)((char *)this + 100) = *(_OWORD *)(v8 + v11 + 16);
      *((_DWORD *)this + 29) = *(_DWORD *)(v8 + v6 + 116);
    }
  }
LABEL_16:
  v5 = WPP_GLOBAL_Control;
LABEL_17:
  if ( v6 )
  {
    WFDFreeMemoryInt(v6);
    v5 = WPP_GLOBAL_Control;
  }
  if ( v5 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v5 + 2), 108, &WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x180013d98  mov     [rsp+arg_10], rbx
0x180013d9d  mov     [rsp+arg_18], rbp
0x180013da2  push    rdi
0x180013da3  sub     rsp, 20h
0x180013da7  mov     rdi, rcx
0x180013daa  mov     rcx, cs:WPP_GLOBAL_Control
0x180013db1  lea     rbp, WPP_GLOBAL_Control
0x180013db8  cmp     rcx, rbp
0x180013dbb  jz      short loc_180013DD8
0x180013dbd  test    byte ptr [rcx+1Ch], 8
0x180013dc1  jz      short loc_180013DD8
0x180013dc3  mov     rcx, [rcx+10h]
0x180013dc7  lea     r8, WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids
0x180013dce  mov     edx, 6Ah ; 'j'
0x180013dd3  call    WPP_SF_
0x180013dd8  mov     rcx, [rdi+38h]
0x180013ddc  lea     r9, [rsp+28h+arg_8]
0x180013de1  lea     r8, [rsp+28h+arg_0]
0x180013de6  mov     [rsp+28h+arg_0], 0
0x180013dee  mov     edx, 4
0x180013df3  mov     [rsp+28h+arg_8], 0
0x180013dfc  call    cs:__imp_WFDQueryPropertyInt
0x180013e02  mov     ebx, eax
0x180013e04  test    eax, eax
0x180013e06  jz      short loc_180013E4B
0x180013e08  jle     short loc_180013E13
0x180013e0a  movzx   ebx, ax
0x180013e0d  or      ebx, 80070000h
0x180013e13  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e1a  cmp     rcx, rbp
0x180013e1d  jz      short loc_180013E44
0x180013e1f  test    byte ptr [rcx+1Ch], 1
0x180013e23  jz      short loc_180013E44
0x180013e25  mov     rcx, [rcx+10h]
0x180013e29  lea     r8, WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids
0x180013e30  mov     edx, 6Bh ; 'k'
0x180013e35  mov     r9d, ebx
0x180013e38  call    WPP_SF_d
0x180013e3d  mov     rdx, [rsp+28h+arg_8]
0x180013e42  jmp     short loc_180013E88
0x180013e44  mov     rdx, [rsp+28h+arg_8]
0x180013e49  jmp     short loc_180013E8F
0x180013e4b  mov     rdx, [rsp+28h+arg_8]
0x180013e50  xor     ecx, ecx
0x180013e52  mov     ebx, 80070490h
0x180013e57  cmp     [rdx+4], ecx
0x180013e5a  jbe     short loc_180013E88
0x180013e5c  mov     eax, ecx
0x180013e5e  imul    rax, 11Ch
0x180013e65  cmp     dword ptr [rax+rdx+0Ch], 2
0x180013e6a  jz      short loc_180013E75
0x180013e6c  inc     ecx
0x180013e6e  cmp     ecx, [rdx+4]
0x180013e71  jb      short loc_180013E5C
0x180013e73  jmp     short loc_180013E88
0x180013e75  movups  xmm0, xmmword ptr [rax+rdx+10h]
0x180013e7a  xor     ebx, ebx
0x180013e7c  movdqu  xmmword ptr [rdi+64h], xmm0
0x180013e81  mov     eax, [rax+rdx+74h]
0x180013e85  mov     [rdi+74h], eax
0x180013e88  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e8f  test    rdx, rdx
0x180013e92  jz      short loc_180013EA4
0x180013e94  mov     rcx, rdx
0x180013e97  call    cs:__imp_WFDFreeMemoryInt
0x180013e9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013ea4  cmp     rcx, rbp
0x180013ea7  jz      short loc_180013EC7
0x180013ea9  test    byte ptr [rcx+1Ch], 8
0x180013ead  jz      short loc_180013EC7
0x180013eaf  mov     rcx, [rcx+10h]
0x180013eb3  lea     r8, WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids
0x180013eba  mov     edx, 6Ch ; 'l'
0x180013ebf  mov     r9d, ebx
0x180013ec2  call    WPP_SF_d
0x180013ec7  mov     rbp, [rsp+28h+arg_18]
0x180013ecc  mov     eax, ebx
0x180013ece  mov     rbx, [rsp+28h+arg_10]
0x180013ed3  add     rsp, 20h
0x180013ed7  pop     rdi
0x180013ed8  retn
```
