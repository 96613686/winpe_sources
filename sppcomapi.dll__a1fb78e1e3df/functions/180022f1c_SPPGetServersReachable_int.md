# SPPGetServersReachable(int *)

- ea: `0x180022f1c`
- end: `0x180023012`
- name: `?SPPGetServersReachable@@YAJPEAH@Z`
- size: `246`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180021600`

## callees

- `0x180003520`
- `0x180004288`
- `0x180021684`
- `0x180022984`
- `0x180022f1c`

## import_xrefs

- `SLC!SLOpen` at `0x180022f54`
- `SLC!SLOpen` at `0x180022f54`
- `SLC!SLClose` at `0x180022ff2`
- `SLC!SLClose` at `0x180022ff2`
- `sppcext!SLGetServerStatus` at `0x180022fb3`
- `sppcext!SLGetServerStatus` at `0x180022fb3`

## pseudocode

```c
__int64 __fastcall SPPGetServersReachable(int *a1)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  unsigned int v4; // esi
  int v5; // edi
  struct SActivationServerAddress *v6; // r12
  HSLC phSLC; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v9; // [rsp+78h] [rbp+38h] BYREF
  HRESULT phrStatus; // [rsp+80h] [rbp+40h] BYREF
  struct SActivationServerAddress *v11; // [rsp+88h] [rbp+48h] BYREF

  phSLC = 0;
  v11 = 0;
  v9 = 0;
  phrStatus = 0;
  v2 = SLOpen(&phSLC);
  v3 = v2;
  if ( v2 < 0 || (v2 = SPPGetServerAddresses(phSLC, &v11, &v9), v3 = v2, v2 < 0) )
  {
LABEL_2:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v2);
    goto LABEL_12;
  }
  v4 = 0;
  v5 = 1;
  if ( v9 )
  {
    v6 = v11;
    do
    {
      v2 = SLGetServerStatus(*((PCWSTR *)v6 + 2 * v4 + 1), *((PCWSTR *)v6 + 2 * v4), 0, 0, &phrStatus);
      v3 = v2;
      if ( v2 < 0 )
        goto LABEL_2;
      if ( phrStatus < 0 )
      {
        v5 = 0;
        break;
      }
    }
    while ( ++v4 < v9 );
  }
  *a1 = v5;
LABEL_12:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v3);
  SP<SActivationServerAddress,SP_CPP_ARRAY<SActivationServerAddress>>::~SP<SActivationServerAddress,SP_CPP_ARRAY<SActivationServerAddress>>(&v11);
  if ( phSLC )
    SLClose(phSLC);
  return v3;
}

```

## disassembly

```asm
0x180022f1c  mov     [rsp-28h+arg_0], rbx
0x180022f21  push    rbp
0x180022f22  push    rsi
0x180022f23  push    rdi
0x180022f24  push    r12
0x180022f26  push    r15
0x180022f28  mov     rbp, rsp
0x180022f2b  sub     rsp, 40h
0x180022f2f  mov     r15, rcx
0x180022f32  mov     [rbp+phSLC], 0
0x180022f3a  lea     rcx, [rbp+phSLC]; phSLC
0x180022f3e  mov     [rbp+arg_18], 0
0x180022f46  mov     [rbp+arg_8], 0
0x180022f4d  mov     [rbp+arg_10], 0
0x180022f54  call    cs:__imp_SLOpen
0x180022f5b  nop     dword ptr [rax+rax+00h]
0x180022f60  mov     ebx, eax
0x180022f62  test    eax, eax
0x180022f64  jns     short loc_180022F6F
0x180022f66  mov     ecx, eax
0x180022f68  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180022f6d  jmp     short loc_180022FD9
0x180022f6f  mov     rcx, [rbp+phSLC]; hSLC
0x180022f73  lea     r8, [rbp+arg_8]; unsigned int *
0x180022f77  lea     rdx, [rbp+arg_18]; struct SActivationServerAddress **
0x180022f7b  call    ?SPPGetServerAddresses@@YAJPEAXPEAPEAUSActivationServerAddress@@PEAK@Z; SPPGetServerAddresses(void *,SActivationServerAddress * *,ulong *)
0x180022f80  mov     ebx, eax
0x180022f82  test    eax, eax
0x180022f84  js      short loc_180022F66
0x180022f86  xor     esi, esi
0x180022f88  mov     edi, 1
0x180022f8d  cmp     [rbp+arg_8], esi
0x180022f90  jbe     short loc_180022FD6
0x180022f92  mov     r12, [rbp+arg_18]
0x180022f96  lea     rcx, [rbp+arg_10]
0x180022f9a  mov     eax, esi
0x180022f9c  add     rax, rax
0x180022f9f  mov     [rsp+40h+phrStatus], rcx; phrStatus
0x180022fa4  xor     r9d, r9d; wProxyPort
0x180022fa7  xor     r8d, r8d; pwszProxyServer
0x180022faa  mov     rdx, [r12+rax*8]; pwszAcquisitionType
0x180022fae  mov     rcx, [r12+rax*8+8]; pwszServerURL
0x180022fb3  call    cs:__imp_SLGetServerStatus
0x180022fba  nop     dword ptr [rax+rax+00h]
0x180022fbf  mov     ebx, eax
0x180022fc1  test    eax, eax
0x180022fc3  js      short loc_180022F66
0x180022fc5  cmp     [rbp+arg_10], 0
0x180022fc9  jl      short loc_180022FD4
0x180022fcb  add     esi, edi
0x180022fcd  cmp     esi, [rbp+arg_8]
0x180022fd0  jb      short loc_180022F96
0x180022fd2  jmp     short loc_180022FD6
0x180022fd4  xor     edi, edi
0x180022fd6  mov     [r15], edi
0x180022fd9  mov     ecx, ebx
0x180022fdb  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180022fe0  lea     rcx, [rbp+arg_18]
0x180022fe4  call    ??1?$SP@USActivationServerAddress@@V?$SP_CPP_ARRAY@USActivationServerAddress@@@@@@QEAA@XZ; SP<SActivationServerAddress,SP_CPP_ARRAY<SActivationServerAddress>>::~SP<SActivationServerAddress,SP_CPP_ARRAY<SActivationServerAddress>>(void)
0x180022fe9  mov     rcx, [rbp+phSLC]; hSLC
0x180022fed  test    rcx, rcx
0x180022ff0  jz      short loc_180022FFE
0x180022ff2  call    cs:__imp_SLClose
0x180022ff9  nop     dword ptr [rax+rax+00h]
0x180022ffe  mov     eax, ebx
0x180023000  mov     rbx, [rsp+40h+arg_0]
0x180023005  add     rsp, 40h
0x180023009  pop     r15
0x18002300b  pop     r12
0x18002300d  pop     rdi
0x18002300e  pop     rsi
0x18002300f  pop     rbp
0x180023010  retn
```
