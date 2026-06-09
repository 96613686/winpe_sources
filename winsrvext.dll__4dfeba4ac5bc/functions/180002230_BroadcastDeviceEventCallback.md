# BroadcastDeviceEventCallback

- ea: `0x180002230`
- end: `0x1800023ba`
- name: `BroadcastDeviceEventCallback`
- size: `394`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180002230`
- `0x180002d20`
- `0x180002f3c`
- `0x1800032cc`
- `0x1800138a1`

## import_xrefs

- `win32u!NtUserSetInformationThread` at `0x180002357`
- `win32u!NtUserSetInformationThread` at `0x1800023a0`
- `win32u!NtUserSetInformationThread` at `0x180002357`
- `win32u!NtUserSetInformationThread` at `0x1800023a0`
- `USER32!BroadcastSystemMessageW` at `0x180002383`
- `USER32!BroadcastSystemMessageW` at `0x180002383`

## pseudocode

```c
__int64 __fastcall BroadcastDeviceEventCallback(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  DWORD Info; // [rsp+30h] [rbp-20h] BYREF
  __int128 v7; // [rsp+38h] [rbp-18h] BYREF
  __int64 v8; // [rsp+48h] [rbp-8h]
  __int64 Buf1; // [rsp+60h] [rbp+10h] BYREF

  Buf1 = a1;
  if ( !memcmp_0(&Buf1, &WNF_PNPA_DEVNODES_CHANGED, 8u) || !memcmp_0(&Buf1, &WNF_PNPA_DEVNODES_CHANGED_SESSION, 8u) )
  {
    Info = 16;
    v8 = 0;
    v7 = 0;
    if ( (int)NtUserSetInformationThread(-2, 7, &v7) >= 0 )
    {
      BroadcastSystemMessageW(0x20000000u, &Info, 0x219u, 7u, 0);
      NtUserSetInformationThread(-2, 9, &v7);
    }
  }
  else if ( !memcmp_0(&Buf1, &WNF_PNPA_VOLUMES_CHANGED, 8u) || !memcmp_0(&Buf1, &WNF_PNPA_VOLUMES_CHANGED_SESSION, 8u) )
  {
    HandleVolumesChangedBroadcast();
  }
  else if ( !memcmp_0(&Buf1, &WNF_PNPA_HARDWAREPROFILES_CHANGED, 8u)
         || !memcmp_0(&Buf1, &WNF_PNPA_HARDWAREPROFILES_CHANGED_SESSION, 8u) )
  {
    HandleHardwareProfilesChangedBroadcast(a5);
  }
  else if ( !memcmp_0(&Buf1, &WNF_PNPA_PORTS_CHANGED, 8u) || !memcmp_0(&Buf1, &WNF_PNPA_PORTS_CHANGED_SESSION, 8u) )
  {
    HandlePortsChangedBroadcast(a5);
  }
  return 0;
}

```

## disassembly

```asm
0x180002230  mov     [rsp-8+arg_8], rbx
0x180002235  mov     [rsp-8+Buf1], rcx
0x18000223a  push    rbp
0x18000223b  mov     rbp, rsp
0x18000223e  sub     rsp, 50h
0x180002242  mov     ebx, 8
0x180002247  lea     rdx, WNF_PNPA_DEVNODES_CHANGED; Buf2
0x18000224e  mov     r8d, ebx; Size
0x180002251  lea     rcx, [rbp+Buf1]; Buf1
0x180002255  call    memcmp_0
0x18000225a  test    eax, eax
0x18000225c  jz      loc_180002332
0x180002262  mov     r8d, ebx; Size
0x180002265  lea     rdx, WNF_PNPA_DEVNODES_CHANGED_SESSION; Buf2
0x18000226c  lea     rcx, [rbp+Buf1]; Buf1
0x180002270  call    memcmp_0
0x180002275  test    eax, eax
0x180002277  jz      loc_180002332
0x18000227d  mov     r8d, ebx; Size
0x180002280  lea     rdx, WNF_PNPA_VOLUMES_CHANGED; Buf2
0x180002287  lea     rcx, [rbp+Buf1]; Buf1
0x18000228b  call    memcmp_0
0x180002290  test    eax, eax
0x180002292  jz      loc_18000232B
0x180002298  mov     r8d, ebx; Size
0x18000229b  lea     rdx, WNF_PNPA_VOLUMES_CHANGED_SESSION; Buf2
0x1800022a2  lea     rcx, [rbp+Buf1]; Buf1
0x1800022a6  call    memcmp_0
0x1800022ab  test    eax, eax
0x1800022ad  jz      short loc_18000232B
0x1800022af  mov     r8d, ebx; Size
0x1800022b2  lea     rdx, WNF_PNPA_HARDWAREPROFILES_CHANGED; Buf2
0x1800022b9  lea     rcx, [rbp+Buf1]; Buf1
0x1800022bd  call    memcmp_0
0x1800022c2  test    eax, eax
0x1800022c4  jz      short loc_18000231D
0x1800022c6  mov     r8d, ebx; Size
0x1800022c9  lea     rdx, WNF_PNPA_HARDWAREPROFILES_CHANGED_SESSION; Buf2
0x1800022d0  lea     rcx, [rbp+Buf1]; Buf1
0x1800022d4  call    memcmp_0
0x1800022d9  test    eax, eax
0x1800022db  jz      short loc_18000231D
0x1800022dd  mov     r8d, ebx; Size
0x1800022e0  lea     rdx, WNF_PNPA_PORTS_CHANGED; Buf2
0x1800022e7  lea     rcx, [rbp+Buf1]; Buf1
0x1800022eb  call    memcmp_0
0x1800022f0  test    eax, eax
0x1800022f2  jz      short loc_18000230F
0x1800022f4  mov     r8d, ebx; Size
0x1800022f7  lea     rdx, WNF_PNPA_PORTS_CHANGED_SESSION; Buf2
0x1800022fe  lea     rcx, [rbp+Buf1]; Buf1
0x180002302  call    memcmp_0
0x180002307  test    eax, eax
0x180002309  jnz     loc_1800023AC
0x18000230f  mov     rcx, [rbp+arg_20]
0x180002313  call    HandlePortsChangedBroadcast
0x180002318  jmp     loc_1800023AC
0x18000231d  mov     rcx, [rbp+arg_20]
0x180002321  call    HandleHardwareProfilesChangedBroadcast
0x180002326  jmp     loc_1800023AC
0x18000232b  call    HandleVolumesChangedBroadcast
0x180002330  jmp     short loc_1800023AC
0x180002332  xor     eax, eax
0x180002334  mov     [rbp+Info], 10h
0x18000233b  xorps   xmm0, xmm0
0x18000233e  mov     [rbp+var_8], rax
0x180002342  lea     r8, [rbp+var_18]
0x180002346  movups  [rbp+var_18], xmm0
0x18000234a  lea     ebx, [rax+18h]
0x18000234d  mov     r9d, ebx
0x180002350  lea     edx, [rax+7]
0x180002353  lea     rcx, [rax-2]
0x180002357  call    cs:__imp_NtUserSetInformationThread
0x18000235e  nop     dword ptr [rax+rax+00h]
0x180002363  test    eax, eax
0x180002365  js      short loc_1800023AC
0x180002367  lea     r9d, [rbx-11h]; wParam
0x18000236b  mov     [rsp+50h+lParam], 0; lParam
0x180002374  mov     r8d, 219h; Msg
0x18000237a  lea     rdx, [rbp+Info]; lpInfo
0x18000237e  mov     ecx, 20000000h; flags
0x180002383  call    cs:__imp_BroadcastSystemMessageW
0x18000238a  nop     dword ptr [rax+rax+00h]
0x18000238f  mov     r9d, ebx
0x180002392  lea     r8, [rbp+var_18]
0x180002396  lea     edx, [rbx-0Fh]
0x180002399  mov     rcx, 0FFFFFFFFFFFFFFFEh
0x1800023a0  call    cs:__imp_NtUserSetInformationThread
0x1800023a7  nop     dword ptr [rax+rax+00h]
0x1800023ac  mov     rbx, [rsp+50h+arg_8]
0x1800023b1  xor     eax, eax
0x1800023b3  add     rsp, 50h
0x1800023b7  pop     rbp
0x1800023b8  retn
```
