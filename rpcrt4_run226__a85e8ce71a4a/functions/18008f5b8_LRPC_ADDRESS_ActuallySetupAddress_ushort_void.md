# LRPC_ADDRESS::ActuallySetupAddress(ushort *,void *)

- ea: `0x18008f5b8`
- end: `0x18008f7ba`
- name: `?ActuallySetupAddress@LRPC_ADDRESS@@AEAAJPEAGPEAX@Z`
- size: `514`
- prototype: `int(LRPC_ADDRESS *__hidden this, unsigned __int16 *, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x18008f420`

## callees

- `0x180021ce0`
- `0x180022870`
- `0x180050454`
- `0x18008f5b8`
- `0x1800ca049`
- `0x1800ca140`

## import_xrefs

- `ntdll!NtAlpcQueryInformation` at `0x18008f709`
- `ntdll!NtAlpcQueryInformation` at `0x18008f709`
- `ntdll!NtAlpcCreatePort` at `0x18008f6c6`
- `ntdll!NtAlpcCreatePort` at `0x18008f6c6`
- `ntdll!RtlInitUnicodeString` at `0x18008f62c`
- `ntdll!RtlInitUnicodeString` at `0x18008f62c`

## pseudocode

```c
__int64 __fastcall LRPC_ADDRESS::ActuallySetupAddress(LRPC_ADDRESS *this, unsigned __int16 *a2, unsigned __int64 a3)
{
  int v6; // ebx
  __int64 result; // rax
  unsigned __int64 v8; // rax
  __int64 v9; // rcx
  int v10; // [rsp+28h] [rbp-81h]
  int v11; // [rsp+30h] [rbp-79h]
  PCWSTR SourceString; // [rsp+40h] [rbp-69h] BYREF
  __int128 v13; // [rsp+48h] [rbp-61h] BYREF
  __int128 v14; // [rsp+58h] [rbp-51h]
  __int128 v15; // [rsp+68h] [rbp-41h]
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-31h] BYREF
  int v17; // [rsp+90h] [rbp-19h] BYREF
  __int64 v18; // [rsp+94h] [rbp-15h]
  __int16 v19; // [rsp+9Ch] [rbp-Dh]
  __int64 v20; // [rsp+A0h] [rbp-9h]
  __int64 v21; // [rsp+A8h] [rbp-1h]
  __int64 v22; // [rsp+B0h] [rbp+7h]
  __int64 v23; // [rsp+B8h] [rbp+Fh]
  __int64 v24; // [rsp+C0h] [rbp+17h]
  __int64 v25; // [rsp+C8h] [rbp+1Fh]
  int v26; // [rsp+D0h] [rbp+27h]

  SourceString = 0;
  DestinationString = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  memset_0(&v17, 0, 0x48u);
  if ( (unsigned int)TransformLrpcEndpointToAlpcPortName(a2, (unsigned __int16 **)&SourceString) )
    return 14;
  RtlInitUnicodeString(&DestinationString, SourceString);
  LODWORD(v13) = 48;
  *(_QWORD *)&v14 = &DestinationString;
  v22 = 0xFFFFFFFFLL;
  v23 = 0xFFFFFFFFLL;
  v25 = 0xFFFFFFFFLL;
  v24 = 0xFFFFFFFFLL;
  *((_QWORD *)&v13 + 1) = 0;
  DWORD2(v14) = 64;
  v15 = a3;
  v17 = 34078720;
  v26 = 4093;
  v20 = 4096;
  v21 = 0;
  v18 = 12;
  v19 = 257;
  if ( (NtCurrentPeb()->ProcessParameters->Flags & 0x80000000) != 0 )
  {
    v17 = 50855936;
    *((_DWORD *)this + 104) = 65280;
    v20 = 65280;
  }
  v6 = NtAlpcCreatePort((char *)this + 208, &v13, &v17);
  LogEvent(0x4Cu, 0x43u, *((void **)this + 26), 0, v6, v10, v11);
  FreeWrapper((void *)SourceString);
  if ( v6 >= 0 )
  {
    NtAlpcQueryInformation(*((_QWORD *)this + 26), 0, (char *)this + 384, 16, 0);
    *((_DWORD *)this + 100) = *((_DWORD *)this + 97);
    return 0;
  }
  if ( v6 == -1073741801 )
    return 14;
  if ( v6 == -1073741670 || v6 == -1073741756 )
    return 1721;
  v8 = (unsigned int)(v6 + 1073741788);
  if ( (unsigned int)v8 <= 0x36 )
  {
    v9 = 0x40000000608001LL;
    if ( _bittest64(&v9, v8) )
      return 1706;
  }
  result = 1740;
  if ( v6 == -1073741727 )
    return 5;
  return result;
}

```

## disassembly

```asm
0x18008f5b8  mov     [rsp-8+arg_18], rbx
0x18008f5bd  push    rbp
0x18008f5be  push    rsi
0x18008f5bf  push    rdi
0x18008f5c0  lea     rbp, [rsp-47h]
0x18008f5c5  sub     rsp, 0F0h
0x18008f5cc  mov     rax, cs:__security_cookie
0x18008f5d3  xor     rax, rsp
0x18008f5d6  mov     [rbp+57h+var_20], rax
0x18008f5da  xorps   xmm1, xmm1
0x18008f5dd  mov     [rbp+57h+SourceString], 0
0x18008f5e5  mov     rbx, rdx
0x18008f5e8  mov     rsi, r8
0x18008f5eb  xor     edx, edx; Val
0x18008f5ed  mov     rdi, rcx
0x18008f5f0  xorps   xmm0, xmm0
0x18008f5f3  lea     rcx, [rbp+57h+var_70]; void *
0x18008f5f7  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18008f5fb  lea     r8d, [rdx+48h]; Size
0x18008f5ff  movups  [rbp+57h+var_B8], xmm1
0x18008f603  movups  [rbp+57h+var_A8], xmm1
0x18008f607  movups  [rbp+57h+var_98], xmm1
0x18008f60b  call    memset_0
0x18008f610  lea     rdx, [rbp+57h+SourceString]; unsigned __int16 **
0x18008f614  mov     rcx, rbx; unsigned __int16 *
0x18008f617  call    ?TransformLrpcEndpointToAlpcPortName@@YAJPEAGPEAPEAG@Z; TransformLrpcEndpointToAlpcPortName(ushort *,ushort * *)
0x18008f61c  test    eax, eax
0x18008f61e  jnz     loc_18008F73C
0x18008f624  mov     rdx, [rbp+57h+SourceString]; SourceString
0x18008f628  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18008f62c  call    cs:__imp_RtlInitUnicodeString
0x18008f632  mov     dword ptr [rbp+57h+var_B8], 30h ; '0'
0x18008f639  lea     rax, [rbp+57h+DestinationString]
0x18008f63d  mov     qword ptr [rbp+57h+var_A8], rax
0x18008f641  mov     eax, 0FFFFFFFFh
0x18008f646  mov     [rbp+57h+var_50], rax
0x18008f64a  mov     [rbp+57h+var_48], rax
0x18008f64e  mov     [rbp+57h+var_38], rax
0x18008f652  mov     [rbp+57h+var_40], rax
0x18008f656  mov     qword ptr [rbp+57h+var_B8+8], 0
0x18008f65e  mov     dword ptr [rbp+57h+var_A8+8], 40h ; '@'
0x18008f665  mov     qword ptr [rbp+57h+var_98], rsi
0x18008f669  mov     qword ptr [rbp+57h+var_98+8], 0
0x18008f671  mov     [rbp+57h+var_70], 2080000h
0x18008f678  mov     [rbp+57h+var_30], 0FFDh
0x18008f67f  mov     [rbp+57h+var_60], 1000h
0x18008f687  mov     [rbp+57h+var_58], 0
0x18008f68f  mov     [rbp+57h+var_6C], 0Ch
0x18008f697  mov     [rbp+57h+var_64], 101h
0x18008f69d  mov     rax, gs:60h
0x18008f6a6  mov     rcx, [rax+20h]
0x18008f6aa  cmp     dword ptr [rcx+8], 0
0x18008f6ae  jl      loc_18008F743
0x18008f6b4  lea     rsi, [rdi+0D0h]
0x18008f6bb  mov     rcx, rsi
0x18008f6be  lea     r8, [rbp+57h+var_70]
0x18008f6c2  lea     rdx, [rbp+57h+var_B8]
0x18008f6c6  call    cs:__imp_NtAlpcCreatePort
0x18008f6cc  mov     r8, [rsi]; void *
0x18008f6cf  xor     r9d, r9d; void *
0x18008f6d2  movsxd  rbx, eax
0x18008f6d5  mov     dl, 43h ; 'C'; unsigned __int8
0x18008f6d7  mov     cl, 4Ch ; 'L'; unsigned __int8
0x18008f6d9  mov     [rsp+100h+var_E0], rbx; unsigned __int64
0x18008f6de  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x18008f6e3  mov     rcx, [rbp+57h+SourceString]; lpMem
0x18008f6e7  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18008f6ec  test    ebx, ebx
0x18008f6ee  js      short loc_18008F75E
0x18008f6f0  mov     rcx, [rsi]
0x18008f6f3  lea     r8, [rdi+180h]
0x18008f6fa  xor     edx, edx
0x18008f6fc  mov     [rsp+100h+var_E0], 0
0x18008f705  lea     r9d, [rdx+10h]
0x18008f709  call    cs:__imp_NtAlpcQueryInformation
0x18008f70f  mov     eax, [rdi+184h]
0x18008f715  mov     [rdi+190h], eax
0x18008f71b  xor     eax, eax
0x18008f71d  mov     rcx, [rbp+57h+var_20]
0x18008f721  xor     rcx, rsp; StackCookie
0x18008f724  call    __security_check_cookie
0x18008f729  mov     rbx, [rsp+100h+arg_18]
0x18008f731  add     rsp, 0F0h
0x18008f738  pop     rdi
0x18008f739  pop     rsi
0x18008f73a  pop     rbp
0x18008f73b  retn
0x18008f73c  mov     eax, 0Eh
0x18008f741  jmp     short loc_18008F71D
0x18008f743  mov     eax, 0FF00h
0x18008f748  mov     [rbp+57h+var_70], 3080000h
0x18008f74f  mov     [rdi+1A0h], eax
0x18008f755  mov     [rbp+57h+var_60], rax
0x18008f759  jmp     loc_18008F6B4
0x18008f75e  cmp     ebx, 0C0000017h
0x18008f764  jz      short loc_18008F73C
0x18008f766  cmp     ebx, 0C000009Ah
0x18008f76c  jz      short loc_18008F7B0
0x18008f76e  cmp     ebx, 0C0000044h
0x18008f774  jz      short loc_18008F7B0
0x18008f776  lea     eax, [rbx+3FFFFFDCh]
0x18008f77c  cmp     eax, 36h ; '6'
0x18008f77f  ja      short loc_18008F798
0x18008f781  mov     rcx, 40000000608001h
0x18008f78b  bt      rcx, rax
0x18008f78f  jnb     short loc_18008F798
0x18008f791  mov     eax, 6AAh
0x18008f796  jmp     short loc_18008F71D
0x18008f798  cmp     ebx, 0C0000061h
0x18008f79e  mov     eax, 6CCh
0x18008f7a3  mov     ecx, 5
0x18008f7a8  cmovz   eax, ecx
0x18008f7ab  jmp     loc_18008F71D
0x18008f7b0  mov     eax, 6B9h
0x18008f7b5  jmp     loc_18008F71D
```
