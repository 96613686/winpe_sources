# HUBUCX_CreateDeviceInUCX

- ea: `0x140025f38`
- end: `0x1400260d7`
- name: `HUBUCX_CreateDeviceInUCX`
- size: `415`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x140021040`

## callees

- `0x1400024b8`
- `0x14000fd4c`
- `0x1400101b8`
- `0x140025f38`
- `0x140045570`

## pseudocode

```c
__int64 __fastcall HUBUCX_CreateDeviceInUCX(__int64 *a1)
{
  __int64 v1; // rbp
  __int64 *v2; // rdi
  __int64 v3; // rsi
  int v5; // eax
  int v6; // edx
  int v7; // edi
  __int64 Flink_low; // [rsp+60h] [rbp+8h]

  v1 = *a1;
  v2 = a1 + 21;
  v3 = a1[1];
  *((_DWORD *)a1 + 42) = 32;
  Flink_low = LODWORD(WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink);
  if ( ((__int64)WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink & 0x10) == 0 )
  {
    LODWORD(Flink_low) = LODWORD(WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink) | 1;
    wil_details_FeatureReporting_ReportUsageToService(&Feature_UISCSF__private_descriptor, Flink_low, 3);
    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(Flink_low, 3, &Feature_UISCSF__private_descriptor);
  }
  v5 = *((_DWORD *)a1 + 366);
  if ( (v5 & 0x800) != 0 )
  {
    *((_DWORD *)a1 + 43) = 3;
    *((_DWORD *)a1 + 40) = 512;
    goto LABEL_11;
  }
  if ( (v5 & 0x100) != 0 )
  {
    *((_DWORD *)a1 + 43) = 2;
    *((_DWORD *)a1 + 48) = 2;
  }
  else
  {
    if ( (v5 & 0x400) != 0 )
    {
      *((_DWORD *)a1 + 43) = 0;
      *((_DWORD *)a1 + 48) = 0;
      *((_DWORD *)a1 + 40) = 8;
      goto LABEL_11;
    }
    *((_DWORD *)a1 + 43) = 1;
    *((_DWORD *)a1 + 48) = 1;
  }
  *((_DWORD *)a1 + 40) = 64;
LABEL_11:
  *((_DWORD *)a1 + 44) = *(unsigned __int16 *)(v3 + 200);
  a1[23] = (__int64)a1;
  v7 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64 *))(v1 + 408))(*(_QWORD *)(v1 + 248), v2, a1 + 3);
  if ( v7 >= 0 )
  {
    a1[193] = a1[3];
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v6) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(a1[1] + 1432),
        v6,
        5,
        38,
        (__int64)WPP_6f1e94dad5dd3d9188df346061fdcafd_Traceguids,
        v7);
    }
    *((_DWORD *)a1 + 393) = -1073737728;
    *((_DWORD *)a1 + 392) = -1073741670;
  }
  return ((v7 >> 31) & 0xFFFFFFF4) + 4077;
}

```

## disassembly

```asm
0x140025f38  push    rbx
0x140025f3a  push    rbp
0x140025f3b  push    rsi
0x140025f3c  push    rdi
0x140025f3d  sub     rsp, 38h
0x140025f41  mov     rbp, [rcx]
0x140025f44  lea     rdi, [rcx+0A8h]
0x140025f4b  mov     rsi, [rcx+8]
0x140025f4f  mov     rbx, rcx
0x140025f52  mov     dword ptr [rdi], 20h ; ' '
0x140025f58  mov     ecx, dword ptr cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink
0x140025f5e  mov     [rsp+58h+arg_0], 0
0x140025f67  mov     dword ptr [rsp+58h+arg_0], ecx
0x140025f6b  test    cl, 10h
0x140025f6e  jnz     short loc_140025FAE
0x140025f70  mov     rax, [rsp+58h+arg_0]
0x140025f75  or      ecx, 1
0x140025f78  mov     [rsp+58h+arg_0], rax
0x140025f7d  mov     r8d, 3
0x140025f83  mov     dword ptr [rsp+58h+arg_0], ecx
0x140025f87  lea     rcx, Feature_UISCSF__private_descriptor
0x140025f8e  mov     rdx, [rsp+58h+arg_0]
0x140025f93  call    wil_details_FeatureReporting_ReportUsageToService
0x140025f98  mov     rcx, [rsp+58h+arg_0]
0x140025f9d  lea     r8, Feature_UISCSF__private_descriptor
0x140025fa4  mov     edx, 3
0x140025fa9  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x140025fae  mov     eax, [rbx+5B8h]
0x140025fb4  bt      eax, 0Bh
0x140025fb8  jnb     short loc_140025FD0
0x140025fba  mov     dword ptr [rbx+0ACh], 3
0x140025fc4  mov     dword ptr [rbx+0A0h], 200h
0x140025fce  jmp     short loc_140026030
0x140025fd0  bt      eax, 8
0x140025fd4  jnb     short loc_140025FEC
0x140025fd6  mov     dword ptr [rbx+0ACh], 2
0x140025fe0  mov     dword ptr [rbx+0C0h], 2
0x140025fea  jmp     short loc_140026026
0x140025fec  bt      eax, 0Ah
0x140025ff0  jnb     short loc_140026012
0x140025ff2  mov     dword ptr [rbx+0ACh], 0
0x140025ffc  mov     dword ptr [rbx+0C0h], 0
0x140026006  mov     dword ptr [rbx+0A0h], 8
0x140026010  jmp     short loc_140026030
0x140026012  mov     dword ptr [rbx+0ACh], 1
0x14002601c  mov     dword ptr [rbx+0C0h], 1
0x140026026  mov     dword ptr [rbx+0A0h], 40h ; '@'
0x140026030  movzx   eax, word ptr [rsi+0C8h]
0x140026037  lea     r8, [rbx+18h]
0x14002603b  mov     [rbx+0B0h], eax
0x140026041  mov     rdx, rdi
0x140026044  mov     [rbx+0B8h], rbx
0x14002604b  mov     rax, [rbp+198h]
0x140026052  mov     rcx, [rbp+0F8h]
0x140026059  call    _guard_dispatch_icall
0x14002605e  mov     edi, eax
0x140026060  test    eax, eax
0x140026062  jns     short loc_1400260B6
0x140026064  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002606b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140026072  jz      short loc_1400260A0
0x140026074  mov     rcx, [rbx+8]
0x140026078  lea     rax, WPP_6f1e94dad5dd3d9188df346061fdcafd_Traceguids
0x14002607f  mov     r9d, 26h ; '&'
0x140026085  mov     [rsp+58h+var_30], edi
0x140026089  mov     dl, 2
0x14002608b  mov     [rsp+58h+var_38], rax
0x140026090  mov     rcx, [rcx+598h]
0x140026097  lea     r8d, [r9-21h]
0x14002609b  call    WPP_RECORDER_SF_d
0x1400260a0  mov     dword ptr [rbx+624h], 0C0001000h
0x1400260aa  mov     dword ptr [rbx+620h], 0C000009Ah
0x1400260b4  jmp     short loc_1400260C1
0x1400260b6  mov     rcx, [rbx+18h]
0x1400260ba  mov     [rbx+608h], rcx
0x1400260c1  sar     edi, 1Fh
0x1400260c4  and     edi, 0FFFFFFF4h
0x1400260c7  lea     eax, [rdi+0FEDh]
0x1400260cd  add     rsp, 38h
0x1400260d1  pop     rdi
0x1400260d2  pop     rsi
0x1400260d3  pop     rbp
0x1400260d4  pop     rbx
0x1400260d5  retn
```
