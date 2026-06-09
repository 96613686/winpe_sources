# SclpFsProcessVolumeByHandle

- ea: `0x180011d8c`
- end: `0x180012043`
- name: `SclpFsProcessVolumeByHandle`
- size: `695`
- prototype: `__int64 __fastcall(__int64, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001188c`

## callees

- `0x180007ebc`
- `0x18000a524`
- `0x180011d8c`
- `0x1800179ad`
- `0x1800179c5`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180011e04`
- `ntdll!RtlAllocateHeap` at `0x180011e04`
- `ntdll!RtlLengthSid` at `0x180011dc0`
- `ntdll!RtlLengthSid` at `0x180011dcc`
- `ntdll!RtlLengthSid` at `0x180011dc0`
- `ntdll!RtlLengthSid` at `0x180011dcc`
- `ntdll!RtlFreeHeap` at `0x180012029`
- `ntdll!RtlFreeHeap` at `0x180012029`
- `ntdll!NtFsControlFile` at `0x180011ec5`
- `ntdll!NtFsControlFile` at `0x180011ec5`

## pseudocode

```c
__int64 __fastcall SclpFsProcessVolumeByHandle(__int64 a1, void *a2)
{
  size_t v4; // rbp
  ULONG v5; // eax
  size_t v6; // r14
  ULONG InputBufferLength; // r15d
  char *Heap; // rax
  _DWORD *InputBuffer; // rsi
  int v10; // ebx
  unsigned __int16 v11; // ax
  __int64 v12; // rbx
  NTSTATUS v13; // eax
  __int64 v14; // rcx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-98h] BYREF
  char OutputBuffer[8]; // [rsp+60h] [rbp-88h] BYREF
  __int64 v18; // [rsp+68h] [rbp-80h]
  __int64 v19; // [rsp+70h] [rbp-78h]
  __int64 v20; // [rsp+80h] [rbp-68h]
  __int64 v21; // [rsp+88h] [rbp-60h]
  __int64 v22; // [rsp+90h] [rbp-58h]
  __int64 v23; // [rsp+98h] [rbp-50h]

  IoStatusBlock = 0;
  memset_0(OutputBuffer, 0, 0x48u);
  v4 = RtlLengthSid(*(PSID *)(a1 + 16));
  v5 = RtlLengthSid(*(PSID *)(a1 + 24));
  v6 = v5;
  InputBufferLength = ((v5 + 7) & 0xFFFFFFF8) + ((v4 + 7) & 0xFFFFFFF8) + 16;
  Heap = (char *)RtlAllocateHeap(
                   NtCurrentPeb()->ProcessHeap,
                   8u,
                   ((v5 + 7) & 0xFFFFFFF8) + (((_DWORD)v4 + 7) & 0xFFFFFFF8) + 16LL);
  InputBuffer = Heap;
  if ( Heap )
  {
    v10 = RtlUIntToUShort((unsigned int)v4, Heap + 10);
    if ( v10 >= 0 )
    {
      v10 = RtlUIntToUShort((unsigned int)v6, (char *)InputBuffer + 14);
      if ( v10 >= 0 )
      {
        InputBuffer[1] = 1;
        *((_WORD *)InputBuffer + 4) = 16;
        v11 = ((v4 + 7) & 0xFFF8) + 16;
        v12 = v11;
        *((_WORD *)InputBuffer + 6) = v11;
        memcpy_0(InputBuffer + 4, *(const void **)(a1 + 16), v4);
        memcpy_0((char *)InputBuffer + v12, *(const void **)(a1 + 24), v6);
        v13 = NtFsControlFile(
                a2,
                0,
                0,
                0,
                &IoStatusBlock,
                0x901F4u,
                InputBuffer,
                InputBufferLength,
                OutputBuffer,
                0x48u);
        v14 = a1 + 1152;
        v10 = v13;
        if ( v13 >= 0 )
        {
          if ( !a1 )
            v14 = 0;
          SclLogGenericMessage(
            v14,
            1,
            (int)SclEvent_Generic_Info,
            501,
            (__int64)"SclpFsProcessVolumeByHandle",
            "FSCTL_SD_GLOBAL_CHANGE succeeded");
          if ( a1 != -1248 )
            *(_QWORD *)(a1 + 1248) += v18;
          if ( a1 != -1256 )
            *(_QWORD *)(a1 + 1256) += v19;
          if ( a1 != -1264 )
            *(_QWORD *)(a1 + 1264) += v20;
          if ( a1 != -1272 )
            *(_QWORD *)(a1 + 1272) += v21;
          if ( a1 != -1280 )
            *(_QWORD *)(a1 + 1280) += v22;
          if ( a1 != -1288 )
            *(_QWORD *)(a1 + 1288) += v23;
        }
        else
        {
          if ( !a1 )
            v14 = 0;
          SclLogGenericMessage(
            v14,
            3,
            (int)SclEvent_Generic_Error,
            488,
            (__int64)"SclpFsProcessVolumeByHandle",
            "(%lx): FSCTL_SD_GLOBAL_CHANGE failed",
            v13);
        }
      }
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, InputBuffer);
  }
  else
  {
    return (unsigned int)-1073741801;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180011d8c  push    rbx
0x180011d8e  push    rbp
0x180011d8f  push    rsi
0x180011d90  push    rdi
0x180011d91  push    r12
0x180011d93  push    r14
0x180011d95  push    r15
0x180011d97  sub     rsp, 0B0h
0x180011d9e  mov     r12, rdx
0x180011da1  mov     rdi, rcx
0x180011da4  xor     edx, edx; Val
0x180011da6  lea     rcx, [rsp+0E8h+var_88]; void *
0x180011dab  xorps   xmm0, xmm0
0x180011dae  movups  xmmword ptr [rsp+0E8h+var_98], xmm0
0x180011db3  lea     r8d, [rdx+48h]; Size
0x180011db7  call    memset_0
0x180011dbc  mov     rcx, [rdi+10h]; Sid
0x180011dc0  call    cs:__imp_RtlLengthSid
0x180011dc6  mov     rcx, [rdi+18h]; Sid
0x180011dca  mov     ebp, eax
0x180011dcc  call    cs:__imp_RtlLengthSid
0x180011dd2  mov     rcx, gs:60h
0x180011ddb  lea     r15d, [rbp+7]
0x180011ddf  mov     r14d, eax
0x180011de2  mov     eax, 0FFFFFFF8h
0x180011de7  and     r15, rax
0x180011dea  add     r15, 10h
0x180011dee  mov     rcx, [rcx+30h]; HeapHandle
0x180011df2  lea     edx, [r14+7]
0x180011df6  and     rdx, rax
0x180011df9  add     r15, rdx
0x180011dfc  mov     edx, 8; Flags
0x180011e01  mov     r8, r15; Size
0x180011e04  call    cs:__imp_RtlAllocateHeap
0x180011e0a  mov     rsi, rax
0x180011e0d  test    rax, rax
0x180011e10  jnz     short loc_180011E1C
0x180011e12  mov     ebx, 0C0000017h
0x180011e17  jmp     loc_18001202F
0x180011e1c  lea     rdx, [rax+0Ah]
0x180011e20  mov     ecx, ebp
0x180011e22  call    RtlUIntToUShort
0x180011e27  mov     ebx, eax
0x180011e29  test    eax, eax
0x180011e2b  js      loc_180012017
0x180011e31  lea     rdx, [rsi+0Eh]
0x180011e35  mov     ecx, r14d
0x180011e38  call    RtlUIntToUShort
0x180011e3d  mov     ebx, eax
0x180011e3f  test    eax, eax
0x180011e41  js      loc_180012017
0x180011e47  mov     edx, 10h
0x180011e4c  mov     dword ptr [rsi+4], 1
0x180011e53  lea     eax, [rbp+7]
0x180011e56  mov     [rsi+8], dx
0x180011e5a  mov     ecx, 0FFF8h
0x180011e5f  mov     r8, rbp; Size
0x180011e62  and     ax, cx
0x180011e65  lea     rcx, [rsi+10h]; void *
0x180011e69  add     ax, dx
0x180011e6c  movzx   ebx, ax
0x180011e6f  mov     [rsi+0Ch], bx
0x180011e73  mov     rdx, [rdi+10h]; Src
0x180011e77  call    memcpy_0
0x180011e7c  mov     rdx, [rdi+18h]; Src
0x180011e80  lea     rcx, [rsi+rbx]; void *
0x180011e84  mov     r8, r14; Size
0x180011e87  call    memcpy_0
0x180011e8c  mov     [rsp+0E8h+OutputBufferLength], 48h ; 'H'; OutputBufferLength
0x180011e94  lea     rax, [rsp+0E8h+var_88]
0x180011e99  mov     [rsp+0E8h+OutputBuffer], rax; OutputBuffer
0x180011e9e  xor     r9d, r9d; ApcContext
0x180011ea1  mov     [rsp+0E8h+InputBufferLength], r15d; InputBufferLength
0x180011ea6  lea     rax, [rsp+0E8h+var_98]
0x180011eab  mov     [rsp+0E8h+InputBuffer], rsi; InputBuffer
0x180011eb0  xor     r8d, r8d; ApcRoutine
0x180011eb3  mov     [rsp+0E8h+FsControlCode], 901F4h; FsControlCode
0x180011ebb  xor     edx, edx; Event
0x180011ebd  mov     rcx, r12; FileHandle
0x180011ec0  mov     [rsp+0E8h+IoStatusBlock], rax; IoStatusBlock
0x180011ec5  call    cs:__imp_NtFsControlFile
0x180011ecb  lea     rcx, [rdi+480h]
0x180011ed2  mov     ebx, eax
0x180011ed4  test    eax, eax
0x180011ed6  jns     short loc_180011F19
0x180011ed8  xor     eax, eax
0x180011eda  mov     dword ptr [rsp+0E8h+InputBuffer], ebx
0x180011ede  test    rdi, rdi
0x180011ee1  lea     r8, SclEvent_Generic_Error
0x180011ee8  mov     r9d, 1E8h
0x180011eee  mov     edx, 3
0x180011ef3  cmovz   rcx, rax
0x180011ef7  lea     rax, aLxFsctlSdGloba; "(%lx): FSCTL_SD_GLOBAL_CHANGE failed"
0x180011efe  mov     qword ptr [rsp+0E8h+FsControlCode], rax
0x180011f03  lea     rax, aSclpfsprocessv; "SclpFsProcessVolumeByHandle"
0x180011f0a  mov     [rsp+0E8h+IoStatusBlock], rax
0x180011f0f  call    SclLogGenericMessage
0x180011f14  jmp     loc_180012017
0x180011f19  xor     eax, eax
0x180011f1b  lea     r8, SclEvent_Generic_Info
0x180011f22  test    rdi, rdi
0x180011f25  mov     r9d, 1F5h
0x180011f2b  mov     edx, 1
0x180011f30  cmovz   rcx, rax
0x180011f34  lea     rax, aFsctlSdGlobalC; "FSCTL_SD_GLOBAL_CHANGE succeeded"
0x180011f3b  mov     qword ptr [rsp+0E8h+FsControlCode], rax
0x180011f40  lea     rax, aSclpfsprocessv; "SclpFsProcessVolumeByHandle"
0x180011f47  mov     [rsp+0E8h+IoStatusBlock], rax
0x180011f4c  call    SclLogGenericMessage
0x180011f51  lea     rax, [rdi+4E0h]
0x180011f58  test    rax, rax
0x180011f5b  jz      short loc_180011F70
0x180011f5d  mov     rax, [rdi+4E0h]
0x180011f64  add     rax, [rsp+0E8h+var_80]
0x180011f69  mov     [rdi+4E0h], rax
0x180011f70  lea     rax, [rdi+4E8h]
0x180011f77  test    rax, rax
0x180011f7a  jz      short loc_180011F8F
0x180011f7c  mov     rax, [rdi+4E8h]
0x180011f83  add     rax, [rsp+0E8h+var_78]
0x180011f88  mov     [rdi+4E8h], rax
0x180011f8f  lea     rax, [rdi+4F0h]
0x180011f96  test    rax, rax
0x180011f99  jz      short loc_180011FB1
0x180011f9b  mov     rax, [rdi+4F0h]
0x180011fa2  add     rax, [rsp+0E8h+var_68]
0x180011faa  mov     [rdi+4F0h], rax
0x180011fb1  lea     rax, [rdi+4F8h]
0x180011fb8  test    rax, rax
0x180011fbb  jz      short loc_180011FD3
0x180011fbd  mov     rax, [rdi+4F8h]
0x180011fc4  add     rax, [rsp+0E8h+var_60]
0x180011fcc  mov     [rdi+4F8h], rax
0x180011fd3  lea     rax, [rdi+500h]
0x180011fda  test    rax, rax
0x180011fdd  jz      short loc_180011FF5
0x180011fdf  mov     rax, [rdi+500h]
0x180011fe6  add     rax, [rsp+0E8h+var_58]
0x180011fee  mov     [rdi+500h], rax
0x180011ff5  lea     rax, [rdi+508h]
0x180011ffc  test    rax, rax
0x180011fff  jz      short loc_180012017
0x180012001  mov     rax, [rdi+508h]
0x180012008  add     rax, [rsp+0E8h+var_50]
0x180012010  mov     [rdi+508h], rax
0x180012017  mov     rcx, gs:60h
0x180012020  mov     r8, rsi; P
0x180012023  xor     edx, edx; Flags
0x180012025  mov     rcx, [rcx+30h]; HeapHandle
0x180012029  call    cs:__imp_RtlFreeHeap
0x18001202f  mov     eax, ebx
0x180012031  add     rsp, 0B0h
0x180012038  pop     r15
0x18001203a  pop     r14
0x18001203c  pop     r12
0x18001203e  pop     rdi
0x18001203f  pop     rsi
0x180012040  pop     rbp
0x180012041  pop     rbx
0x180012042  retn
```
