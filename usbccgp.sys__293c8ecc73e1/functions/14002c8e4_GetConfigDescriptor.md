# GetConfigDescriptor

- ea: `0x14002c8e4`
- end: `0x14002ca7d`
- name: `GetConfigDescriptor`
- size: `409`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140028f7c`

## callees

- `0x14000a6cc`
- `0x14000c2bc`
- `0x14000f664`
- `0x1400115c8`
- `0x1400116a4`
- `0x14002c8e4`
- `0x14002ca84`

## pseudocode

```c
__int64 __fastcall GetConfigDescriptor(__int64 a1, char a2)
{
  unsigned int v4; // ebx
  unsigned int i; // edi
  int ConfigDescriptor; // eax
  int v7; // edx
  int v8; // r8d
  int v9; // r9d
  int v11; // [rsp+20h] [rbp-30h]
  int Src; // [rsp+28h] [rbp-28h]
  size_t Size; // [rsp+30h] [rbp-20h]
  int v14[4]; // [rsp+40h] [rbp-10h] BYREF
  char v15; // [rsp+90h] [rbp+40h] BYREF
  size_t v16; // [rsp+98h] [rbp+48h] BYREF

  v15 = 0;
  v14[0] = 0;
  v4 = -1073741823;
  LODWORD(v16) = 0;
  for ( i = 1; i <= 3; ++i )
  {
    ConfigDescriptor = TryGetConfigDescriptor(a1, a2, &v15, v14, (unsigned int *)&v16);
    v4 = ConfigDescriptor;
    if ( ConfigDescriptor >= 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v7) = 4;
        WPP_RECORDER_SF_d(
          *(_QWORD *)(a1 + 1368),
          v7,
          1,
          28,
          (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids,
          i);
      }
      return v4;
    }
    if ( i >= 3 )
    {
      if ( v15 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_dD(*(_QWORD *)(a1 + 1368), v7, v8, v9, v11, Src, ConfigDescriptor);
        LODWORD(Size) = v16;
        RecordStartFailData(a1, v4, v14[0], -1610612730, 1128552006, *(void **)(a1 + 48), Size);
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v7) = 2;
          WPP_RECORDER_SF_dd(
            *(_QWORD *)(a1 + 1368),
            v7,
            8,
            31,
            (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids,
            3,
            ConfigDescriptor);
        }
        LODWORD(Size) = v16;
        RecordStartFailData(a1, v4, v14[0], -1610612735, 1195590726, *(void **)(a1 + 48), Size);
      }
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_ddd(
          *(_QWORD *)(a1 + 1368),
          v7,
          v8,
          29,
          (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids,
          a2,
          ConfigDescriptor,
          i);
      v15 = 0;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x14002c8e4  mov     [rsp-28h+arg_0], rbx
0x14002c8e9  push    rbp
0x14002c8ea  push    rsi
0x14002c8eb  push    rdi
0x14002c8ec  push    r12
0x14002c8ee  push    r14
0x14002c8f0  mov     rbp, rsp
0x14002c8f3  sub     rsp, 50h
0x14002c8f7  movzx   r14d, dl
0x14002c8fb  lea     r12, WPP_RECORDER_INITIALIZED
0x14002c902  mov     rsi, rcx
0x14002c905  mov     [rbp+arg_10], 0
0x14002c909  mov     [rbp+var_10], 0
0x14002c910  mov     ebx, 0C0000001h
0x14002c915  mov     dword ptr [rbp+arg_18], 0
0x14002c91c  mov     edi, 1
0x14002c921  cmp     edi, 3
0x14002c924  ja      short loc_14002C979
0x14002c926  lea     rax, [rbp+arg_18]
0x14002c92a  mov     dl, r14b
0x14002c92d  lea     r9, [rbp+var_10]
0x14002c931  mov     qword ptr [rsp+50h+var_30], rax
0x14002c936  lea     r8, [rbp+arg_10]
0x14002c93a  mov     rcx, rsi
0x14002c93d  call    TryGetConfigDescriptor
0x14002c942  mov     ebx, eax
0x14002c944  test    eax, eax
0x14002c946  js      short loc_14002C990
0x14002c948  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14002c94f  jz      short loc_14002C979
0x14002c951  mov     rcx, [rsi+558h]
0x14002c958  lea     rax, WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids
0x14002c95f  mov     r9d, 1Ch
0x14002c965  mov     dword ptr [rsp+50h+Src], edi
0x14002c969  mov     dl, 4
0x14002c96b  mov     qword ptr [rsp+50h+var_30], rax
0x14002c970  lea     r8d, [r9-1Bh]
0x14002c974  call    WPP_RECORDER_SF_d
0x14002c979  mov     eax, ebx
0x14002c97b  mov     rbx, [rsp+50h+arg_0]
0x14002c983  add     rsp, 50h
0x14002c987  pop     r14
0x14002c989  pop     r12
0x14002c98b  pop     rdi
0x14002c98c  pop     rsi
0x14002c98d  pop     rbp
0x14002c98e  retn
0x14002c990  cmp     edi, 3
0x14002c993  jnb     short loc_14002C9D2
0x14002c995  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14002c99c  jz      short loc_14002C9C9
0x14002c99e  mov     rcx, [rsi+558h]
0x14002c9a5  lea     rax, WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids
0x14002c9ac  mov     [rsp+50h+var_18], edi
0x14002c9b0  mov     r9d, 1Dh
0x14002c9b6  mov     dword ptr [rsp+50h+Size], ebx
0x14002c9ba  mov     dword ptr [rsp+50h+Src], r14d
0x14002c9bf  mov     qword ptr [rsp+50h+var_30], rax
0x14002c9c4  call    WPP_RECORDER_SF_ddd
0x14002c9c9  mov     [rbp+arg_10], 0
0x14002c9cd  jmp     loc_14002CA76
0x14002c9d2  cmp     [rbp+arg_10], 0
0x14002c9d6  jz      short loc_14002CA11
0x14002c9d8  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14002c9df  jz      short loc_14002C9F1
0x14002c9e1  mov     rcx, [rsi+558h]
0x14002c9e8  mov     dword ptr [rsp+50h+Size], ebx
0x14002c9ec  call    WPP_RECORDER_SF_dD
0x14002c9f1  mov     eax, dword ptr [rbp+arg_18]
0x14002c9f4  mov     r9d, 0A0000006h
0x14002c9fa  mov     dword ptr [rsp+50h+Size], eax
0x14002c9fe  mov     rax, [rsi+30h]
0x14002ca02  mov     [rsp+50h+Src], rax
0x14002ca07  mov     [rsp+50h+var_30], 43445646h
0x14002ca0f  jmp     short loc_14002CA68
0x14002ca11  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14002ca18  jz      short loc_14002CA4A
0x14002ca1a  mov     rcx, [rsi+558h]
0x14002ca21  lea     rax, WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids
0x14002ca28  mov     r9d, 1Fh
0x14002ca2e  mov     dword ptr [rsp+50h+Size], ebx
0x14002ca32  mov     dword ptr [rsp+50h+Src], 3
0x14002ca3a  mov     dl, 2
0x14002ca3c  mov     qword ptr [rsp+50h+var_30], rax
0x14002ca41  lea     r8d, [r9-17h]
0x14002ca45  call    WPP_RECORDER_SF_dd
0x14002ca4a  mov     eax, dword ptr [rbp+arg_18]
0x14002ca4d  mov     r9d, 0A0000001h; int
0x14002ca53  mov     dword ptr [rsp+50h+Size], eax; Size
0x14002ca57  mov     rax, [rsi+30h]
0x14002ca5b  mov     [rsp+50h+Src], rax; Src
0x14002ca60  mov     [rsp+50h+var_30], 47434446h; int
0x14002ca68  mov     r8d, [rbp+var_10]; int
0x14002ca6c  mov     edx, ebx; int
0x14002ca6e  mov     rcx, rsi; int
0x14002ca71  call    RecordStartFailData
0x14002ca76  inc     edi
0x14002ca78  jmp     loc_14002C921
```
