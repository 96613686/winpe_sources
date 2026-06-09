# LRPC_ADDRESS::ActuallySetupAddress(ushort *,void *)

- ea: `0x180093b40`
- end: `0x180093d55`
- name: `?ActuallySetupAddress@LRPC_ADDRESS@@AEAAJPEAGPEAX@Z`
- size: `533`
- prototype: `__int64 __fastcall(LRPC_ADDRESS *this, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1800939a0`

## callees

- `0x180010e48`
- `0x180022e80`
- `0x180023a40`
- `0x180093b40`
- `0x1800ceca9`
- `0x1800ceda0`

## import_xrefs

- `ntdll!NtAlpcQueryInformation` at `0x180093c9d`
- `ntdll!NtAlpcQueryInformation` at `0x180093c9d`
- `ntdll!NtAlpcCreatePort` at `0x180093c54`
- `ntdll!NtAlpcCreatePort` at `0x180093c54`
- `ntdll!RtlInitUnicodeString` at `0x180093bb4`
- `ntdll!RtlInitUnicodeString` at `0x180093bb4`

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
0x180093b40  mov     [rsp-8+arg_18], rbx
0x180093b45  push    rbp
0x180093b46  push    rsi
0x180093b47  push    rdi
0x180093b48  lea     rbp, [rsp-47h]
0x180093b4d  sub     rsp, 0F0h
0x180093b54  mov     rax, cs:__security_cookie
0x180093b5b  xor     rax, rsp
0x180093b5e  mov     [rbp+57h+var_20], rax
0x180093b62  xorps   xmm1, xmm1
0x180093b65  mov     [rbp+57h+SourceString], 0
0x180093b6d  mov     rbx, rdx
0x180093b70  mov     rsi, r8
0x180093b73  xor     edx, edx; Val
0x180093b75  mov     rdi, rcx
0x180093b78  xorps   xmm0, xmm0
0x180093b7b  lea     rcx, [rbp+57h+var_70]; void *
0x180093b7f  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180093b83  lea     r8d, [rdx+48h]; Size
0x180093b87  movups  [rbp+57h+var_B8], xmm1
0x180093b8b  movups  [rbp+57h+var_A8], xmm1
0x180093b8f  movups  [rbp+57h+var_98], xmm1
0x180093b93  call    memset_0
0x180093b98  lea     rdx, [rbp+57h+SourceString]; unsigned __int16 **
0x180093b9c  mov     rcx, rbx; unsigned __int16 *
0x180093b9f  call    ?TransformLrpcEndpointToAlpcPortName@@YAJPEAGPEAPEAG@Z; TransformLrpcEndpointToAlpcPortName(ushort *,ushort * *)
0x180093ba4  test    eax, eax
0x180093ba6  jnz     loc_180093CD7
0x180093bac  mov     rdx, [rbp+57h+SourceString]; SourceString
0x180093bb0  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180093bb4  call    cs:__imp_RtlInitUnicodeString
0x180093bbb  nop     dword ptr [rax+rax+00h]
0x180093bc0  mov     dword ptr [rbp+57h+var_B8], 30h ; '0'
0x180093bc7  lea     rax, [rbp+57h+DestinationString]
0x180093bcb  mov     qword ptr [rbp+57h+var_A8], rax
0x180093bcf  mov     eax, 0FFFFFFFFh
0x180093bd4  mov     [rbp+57h+var_50], rax
0x180093bd8  mov     [rbp+57h+var_48], rax
0x180093bdc  mov     [rbp+57h+var_38], rax
0x180093be0  mov     [rbp+57h+var_40], rax
0x180093be4  mov     qword ptr [rbp+57h+var_B8+8], 0
0x180093bec  mov     dword ptr [rbp+57h+var_A8+8], 40h ; '@'
0x180093bf3  mov     qword ptr [rbp+57h+var_98], rsi
0x180093bf7  mov     qword ptr [rbp+57h+var_98+8], 0
0x180093bff  mov     [rbp+57h+var_70], 2080000h
0x180093c06  mov     [rbp+57h+var_30], 0FFDh
0x180093c0d  mov     [rbp+57h+var_60], 1000h
0x180093c15  mov     [rbp+57h+var_58], 0
0x180093c1d  mov     [rbp+57h+var_6C], 0Ch
0x180093c25  mov     [rbp+57h+var_64], 101h
0x180093c2b  mov     rax, gs:60h
0x180093c34  mov     rcx, [rax+20h]
0x180093c38  cmp     dword ptr [rcx+8], 0
0x180093c3c  jl      loc_180093CDE
0x180093c42  lea     rsi, [rdi+0D0h]
0x180093c49  mov     rcx, rsi
0x180093c4c  lea     r8, [rbp+57h+var_70]
0x180093c50  lea     rdx, [rbp+57h+var_B8]
0x180093c54  call    cs:__imp_NtAlpcCreatePort
0x180093c5b  nop     dword ptr [rax+rax+00h]
0x180093c60  mov     r8, [rsi]; void *
0x180093c63  xor     r9d, r9d; void *
0x180093c66  movsxd  rbx, eax
0x180093c69  mov     dl, 43h ; 'C'; unsigned __int8
0x180093c6b  mov     cl, 4Ch ; 'L'; unsigned __int8
0x180093c6d  mov     [rsp+100h+var_E0], rbx; unsigned __int64
0x180093c72  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x180093c77  mov     rcx, [rbp+57h+SourceString]; lpMem
0x180093c7b  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x180093c80  test    ebx, ebx
0x180093c82  js      short loc_180093CF9
0x180093c84  mov     rcx, [rsi]
0x180093c87  lea     r8, [rdi+180h]
0x180093c8e  xor     edx, edx
0x180093c90  mov     [rsp+100h+var_E0], 0
0x180093c99  lea     r9d, [rdx+10h]
0x180093c9d  call    cs:__imp_NtAlpcQueryInformation
0x180093ca4  nop     dword ptr [rax+rax+00h]
0x180093ca9  mov     eax, [rdi+184h]
0x180093caf  mov     [rdi+190h], eax
0x180093cb5  xor     eax, eax
0x180093cb7  mov     rcx, [rbp+57h+var_20]
0x180093cbb  xor     rcx, rsp; StackCookie
0x180093cbe  call    __security_check_cookie
0x180093cc3  mov     rbx, [rsp+100h+arg_18]
0x180093ccb  add     rsp, 0F0h
0x180093cd2  pop     rdi
0x180093cd3  pop     rsi
0x180093cd4  pop     rbp
0x180093cd5  retn
0x180093cd7  mov     eax, 0Eh
0x180093cdc  jmp     short loc_180093CB7
0x180093cde  mov     eax, 0FF00h
0x180093ce3  mov     [rbp+57h+var_70], 3080000h
0x180093cea  mov     [rdi+1A0h], eax
0x180093cf0  mov     [rbp+57h+var_60], rax
0x180093cf4  jmp     loc_180093C42
0x180093cf9  cmp     ebx, 0C0000017h
0x180093cff  jz      short loc_180093CD7
0x180093d01  cmp     ebx, 0C000009Ah
0x180093d07  jz      short loc_180093D4B
0x180093d09  cmp     ebx, 0C0000044h
0x180093d0f  jz      short loc_180093D4B
0x180093d11  lea     eax, [rbx+3FFFFFDCh]
0x180093d17  cmp     eax, 36h ; '6'
0x180093d1a  ja      short loc_180093D33
0x180093d1c  mov     rcx, 40000000608001h
0x180093d26  bt      rcx, rax
0x180093d2a  jnb     short loc_180093D33
0x180093d2c  mov     eax, 6AAh
0x180093d31  jmp     short loc_180093CB7
0x180093d33  cmp     ebx, 0C0000061h
0x180093d39  mov     eax, 6CCh
0x180093d3e  mov     ecx, 5
0x180093d43  cmovz   eax, ecx
0x180093d46  jmp     loc_180093CB7
0x180093d4b  mov     eax, 6B9h
0x180093d50  jmp     loc_180093CB7
```
