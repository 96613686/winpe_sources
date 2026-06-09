# SampImpersonateClient

- ea: `0x18001cfa0`
- end: `0x18001d0be`
- name: `SampImpersonateClient`
- size: `286`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `17`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180003d40`
- `0x180005a80`
- `0x1800066f0`
- `0x180007bd0`
- `0x18000a570`
- `0x180011a00`
- `0x18001ca48`
- `0x18001cc00`
- `0x18001ce50`
- `0x18005c180`
- `0x180075264`
- `0x18008c6c0`
- `0x18008cd00`
- `0x18008ed40`
- `0x18009f4fc`
- `0x18009f64c`
- `0x1800a71e0`

## callees

- `0x180012a28`
- `0x18001cfa0`
- `0x180027e24`
- `0x1800372ac`
- `0x180077790`
- `0x18008ec80`

## import_xrefs

- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001d066`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001d066`
- `RPCRT4!I_RpcMapWin32Status` at `0x18001cfd6`
- `RPCRT4!I_RpcMapWin32Status` at `0x18001d06e`
- `RPCRT4!I_RpcMapWin32Status` at `0x18001cfd6`
- `RPCRT4!I_RpcMapWin32Status` at `0x18001d06e`
- `RPCRT4!RpcImpersonateClient` at `0x18001cfce`
- `RPCRT4!RpcImpersonateClient` at `0x18001cfce`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtImpersonateAnyClient` at `0x18001d054`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtImpersonateAnyClient` at `0x18001d054`

## pseudocode

```c
__int64 __fastcall SampImpersonateClient(int *a1)
{
  bool v2; // bl
  RPC_STATUS v3; // eax
  int v4; // ebx
  int v5; // eax
  int v7; // eax
  ULONG v8; // eax
  NTSTATUS v9; // ecx

  v2 = SampUseDsData && !SampDsStopped;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 74, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, v2);
  if ( v2 && (unsigned int)SampExtThreadStateQueryDs() )
  {
    v7 = SampShouldCallNtdsaApiSet();
    if ( v7 < 0 )
    {
      v9 = 0;
      if ( v7 != -1073741637 )
        v9 = v7;
      v8 = RtlNtStatusToDosErrorNoTeb(v9);
    }
    else
    {
      v8 = NtdsaExtImpersonateAnyClient();
    }
    v4 = I_RpcMapWin32Status(v8);
    v5 = 3;
  }
  else
  {
    v3 = RpcImpersonateClient(0);
    v4 = I_RpcMapWin32Status(v3);
    v5 = 2;
  }
  *a1 = v5;
  if ( v4 == -1073610687 )
  {
    v4 = SamIImpersonateNullSession();
    *a1 = 1;
  }
  if ( v4 < 0 )
    *a1 = 0;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 66, WPP_5505de3e48bd33375e96ca021b170945_Traceguids, (unsigned int)v4, v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001cfa0  mov     [rsp+arg_0], rbx
0x18001cfa5  push    rdi
0x18001cfa6  sub     rsp, 30h
0x18001cfaa  cmp     cs:?SampUseDsData@@3EA, 0; uchar SampUseDsData
0x18001cfb1  mov     rdi, rcx
0x18001cfb4  jnz     short loc_18001D01A
0x18001cfb6  xor     bl, bl
0x18001cfb8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cfbf  test    dword ptr [rcx+44h], 20000h
0x18001cfc6  jnz     short loc_18001D027
0x18001cfc8  test    bl, bl
0x18001cfca  jnz     short loc_18001D042
0x18001cfcc  xor     ecx, ecx; BindingHandle
0x18001cfce  call    cs:__imp_RpcImpersonateClient
0x18001cfd4  mov     ecx, eax; Status
0x18001cfd6  call    cs:__imp_I_RpcMapWin32Status
0x18001cfdc  mov     ebx, eax
0x18001cfde  mov     eax, 2
0x18001cfe3  mov     [rdi], eax
0x18001cfe5  cmp     ebx, 0C0020041h
0x18001cfeb  jz      loc_18001D080
0x18001cff1  test    ebx, ebx
0x18001cff3  js      loc_18001D092
0x18001cff9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d000  test    dword ptr [rcx+44h], 20000h
0x18001d007  jnz     loc_18001D09D
0x18001d00d  mov     eax, ebx
0x18001d00f  mov     rbx, [rsp+38h+arg_0]
0x18001d014  add     rsp, 30h
0x18001d018  pop     rdi
0x18001d019  retn
0x18001d01a  cmp     cs:?SampDsStopped@@3EA, 0; uchar SampDsStopped
0x18001d021  jnz     short loc_18001CFB6
0x18001d023  mov     bl, 1
0x18001d025  jmp     short loc_18001CFB8
0x18001d027  mov     rcx, [rcx+38h]
0x18001d02b  lea     r8, WPP_6405431812663459a7a3c2922bf567cd_Traceguids
0x18001d032  movzx   r9d, bl
0x18001d036  mov     edx, 4Ah ; 'J'
0x18001d03b  call    WPP_SF_d
0x18001d040  jmp     short loc_18001CFC8
0x18001d042  call    ?SampExtThreadStateQueryDs@@YAHXZ; SampExtThreadStateQueryDs(void)
0x18001d047  test    eax, eax
0x18001d049  jz      short loc_18001CFCC
0x18001d04b  call    ?SampShouldCallNtdsaApiSet@@YAJXZ; SampShouldCallNtdsaApiSet(void)
0x18001d050  test    eax, eax
0x18001d052  js      short loc_18001D05C
0x18001d054  call    cs:__imp_NtdsaExtImpersonateAnyClient
0x18001d05a  jmp     short loc_18001D06C
0x18001d05c  xor     ecx, ecx
0x18001d05e  cmp     eax, 0C00000BBh
0x18001d063  cmovnz  ecx, eax; Status
0x18001d066  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18001d06c  mov     ecx, eax; Status
0x18001d06e  call    cs:__imp_I_RpcMapWin32Status
0x18001d074  mov     ebx, eax
0x18001d076  mov     eax, 3
0x18001d07b  jmp     loc_18001CFE3
0x18001d080  call    SamIImpersonateNullSession
0x18001d085  mov     ebx, eax
0x18001d087  mov     dword ptr [rdi], 1
0x18001d08d  jmp     loc_18001CFF1
0x18001d092  mov     dword ptr [rdi], 0
0x18001d098  jmp     loc_18001CFF9
0x18001d09d  mov     rcx, [rcx+38h]
0x18001d0a1  lea     r8, WPP_5505de3e48bd33375e96ca021b170945_Traceguids
0x18001d0a8  mov     edx, 42h ; 'B'
0x18001d0ad  mov     [rsp+38h+var_18], ebx
0x18001d0b1  mov     r9d, ebx
0x18001d0b4  call    WPP_SF_Dd
0x18001d0b9  jmp     loc_18001D00D
```
