# TpmTransportMemBase::TreeVendorExecuteCommand(void)

- ea: `0x140019e38`
- end: `0x140019fea`
- name: `?TreeVendorExecuteCommand@TpmTransportMemBase@@AEAAJXZ`
- size: `434`
- prototype: `__int64 __fastcall(TpmTransportMemBase *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000d130`

## callees

- `0x1400078b8`
- `0x140019e38`
- `0x140039780`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140019f33`
- `ntoskrnl!KeWaitForSingleObject` at `0x140019f33`
- `ntoskrnl!KeResetEvent` at `0x140019ecd`
- `ntoskrnl!KeResetEvent` at `0x140019ecd`

## pseudocode

```c
__int64 __fastcall TpmTransportMemBase::TreeVendorExecuteCommand(TpmTransportMemBase *this)
{
  __int64 v2; // rdx
  __int64 v3; // rax
  unsigned int *v4; // rdi
  PDEVICE_OBJECT v5; // rcx
  __int64 v6; // rdx
  __int64 result; // rax
  int v8; // esi
  union _LARGE_INTEGER v9; // rax
  NTSTATUS v10; // eax
  union _LARGE_INTEGER v11; // rcx
  __int64 v12; // rdx
  union _LARGE_INTEGER Timeout; // [rsp+50h] [rbp+8h] BYREF

  v2 = *((_QWORD *)this + 62);
  Timeout.QuadPart = 0;
  v3 = (*((__int64 (__fastcall **)(PKDPC, __int64, void *))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 202))(
         WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
         v2,
         off_1400470F0);
  v4 = (unsigned int *)v3;
  if ( *(_BYTE *)(v3 + 32) )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      return 3221225862LL;
    v6 = 55;
    goto LABEL_5;
  }
  *(_BYTE *)(v3 + 32) = 1;
  v8 = 5;
  KeResetEvent((PRKEVENT)(v3 + 8));
  (*((void (__fastcall **)(PKDPC, _QWORD))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 380))(
    WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
    *((_QWORD *)this + 62));
  v9.QuadPart = MEMORY[0xFFFFF78000000008] - *((_QWORD *)this + 63);
  while ( 2 )
  {
    for ( Timeout = v9; ; Timeout.QuadPart = -v11.QuadPart )
    {
      while ( 1 )
      {
        v10 = KeWaitForSingleObject(v4 + 2, Executive, 0, 0, &Timeout);
        if ( v10 == 258 )
          break;
        if ( !v10 )
        {
          result = *v4;
          *((_BYTE *)v4 + 32) = 0;
          return result;
        }
      }
      v11.QuadPart = *((_QWORD *)this + 63) - MEMORY[0xFFFFF78000000008];
      Timeout = v11;
      if ( v11.QuadPart <= 0 )
        break;
    }
    if ( *((_DWORD *)this + 65) && v8 )
    {
      --v8;
      v12 = *((unsigned int *)this + 62);
      *((_QWORD *)this + 63) = MEMORY[0xFFFFF78000000008] + 10000 * v12;
      v9.QuadPart = -10000 * v12;
      continue;
    }
    break;
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    v6 = 56;
LABEL_5:
    WPP_SF_(v5->AttachedDevice, v6, WPP_8de2460abc9d340e43d1e35357ca3f8a_Traceguids);
  }
  return 3221225862LL;
}

```

## disassembly

```asm
0x140019e38  mov     [rsp+arg_8], rbx
0x140019e3d  mov     [rsp+arg_10], rbp
0x140019e42  push    rsi
0x140019e43  push    rdi
0x140019e44  push    r15
0x140019e46  sub     rsp, 30h
0x140019e4a  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x140019e51  mov     rbx, rcx
0x140019e54  mov     rdx, [rcx+1F0h]
0x140019e5b  mov     r8, cs:off_1400470F0
0x140019e62  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x140019e69  mov     qword ptr [rsp+48h+arg_0], 0
0x140019e72  mov     rax, [rax+650h]
0x140019e79  call    _guard_dispatch_icall
0x140019e7e  mov     rdi, rax
0x140019e81  cmp     byte ptr [rax+20h], 0
0x140019e85  jz      short loc_140019EC0
0x140019e87  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140019e8e  lea     rax, WPP_GLOBAL_Control
0x140019e95  cmp     rcx, rax
0x140019e98  jz      short loc_140019EB6
0x140019e9a  mov     eax, [rcx+2Ch]
0x140019e9d  test    al, 1
0x140019e9f  jz      short loc_140019EB6
0x140019ea1  mov     edx, 37h ; '7'
0x140019ea6  mov     rcx, [rcx+18h]
0x140019eaa  lea     r8, WPP_8de2460abc9d340e43d1e35357ca3f8a_Traceguids
0x140019eb1  call    WPP_SF_
0x140019eb6  mov     eax, 0C0000186h
0x140019ebb  jmp     loc_140019FAA
0x140019ec0  lea     rcx, [rax+8]; Event
0x140019ec4  mov     byte ptr [rax+20h], 1
0x140019ec8  mov     esi, 5
0x140019ecd  call    cs:__imp_KeResetEvent
0x140019ed4  nop     dword ptr [rax+rax+00h]
0x140019ed9  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x140019ee0  mov     rdx, [rbx+1F0h]
0x140019ee7  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x140019eee  mov     rax, [rax+0BE0h]
0x140019ef5  call    _guard_dispatch_icall
0x140019efa  mov     rcx, [rbx+1F8h]
0x140019f01  mov     r15, 0FFFFF78000000008h
0x140019f0b  mov     rax, ds:0FFFFF78000000008h
0x140019f15  sub     rax, rcx
0x140019f18  mov     qword ptr [rsp+48h+arg_0], rax
0x140019f1d  lea     rax, [rsp+48h+arg_0]
0x140019f22  xor     r9d, r9d; Alertable
0x140019f25  xor     r8d, r8d; WaitMode
0x140019f28  mov     [rsp+48h+Timeout], rax; Timeout
0x140019f2d  xor     edx, edx; WaitReason
0x140019f2f  lea     rcx, [rdi+8]; Object
0x140019f33  call    cs:__imp_KeWaitForSingleObject
0x140019f3a  nop     dword ptr [rax+rax+00h]
0x140019f3f  cmp     eax, 102h
0x140019f44  jnz     short loc_140019F9C
0x140019f46  mov     rax, [r15]
0x140019f49  mov     rcx, [rbx+1F8h]
0x140019f50  sub     rcx, rax
0x140019f53  mov     qword ptr [rsp+48h+arg_0], rcx
0x140019f58  test    rcx, rcx
0x140019f5b  jle     short loc_140019F67
0x140019f5d  neg     rcx
0x140019f60  mov     qword ptr [rsp+48h+arg_0], rcx
0x140019f65  jmp     short loc_140019F1D
0x140019f67  cmp     dword ptr [rbx+104h], 0
0x140019f6e  jz      short loc_140019FBE
0x140019f70  test    esi, esi
0x140019f72  jz      short loc_140019FBE
0x140019f74  mov     rax, [r15]
0x140019f77  dec     esi
0x140019f79  mov     edx, [rbx+0F8h]
0x140019f7f  imul    rcx, rdx, 2710h
0x140019f86  add     rcx, rax
0x140019f89  mov     [rbx+1F8h], rcx
0x140019f90  imul    rax, rdx, 0FFFFFFFFFFFFD8F0h
0x140019f97  jmp     loc_140019F18
0x140019f9c  test    eax, eax
0x140019f9e  jnz     loc_140019F1D
0x140019fa4  mov     eax, [rdi]
0x140019fa6  mov     byte ptr [rdi+20h], 0
0x140019faa  mov     rbx, [rsp+48h+arg_8]
0x140019faf  mov     rbp, [rsp+48h+arg_10]
0x140019fb4  add     rsp, 30h
0x140019fb8  pop     r15
0x140019fba  pop     rdi
0x140019fbb  pop     rsi
0x140019fbc  retn
0x140019fbe  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140019fc5  lea     rax, WPP_GLOBAL_Control
0x140019fcc  cmp     rcx, rax
0x140019fcf  jz      loc_140019EB6
0x140019fd5  mov     eax, [rcx+2Ch]
0x140019fd8  test    al, 1
0x140019fda  jz      loc_140019EB6
0x140019fe0  mov     edx, 38h ; '8'
0x140019fe5  jmp     loc_140019EA6
```
