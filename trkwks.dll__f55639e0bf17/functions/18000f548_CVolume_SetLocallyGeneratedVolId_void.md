# CVolume::SetLocallyGeneratedVolId(void)

- ea: `0x18000f548`
- end: `0x18000f5f3`
- name: `?SetLocallyGeneratedVolId@CVolume@@QEAAXXZ`
- size: `171`
- prototype: `void __fastcall(CVolume *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180002488`

## callees

- `0x1800028f0`
- `0x180002f24`
- `0x18000d038`
- `0x18000da64`
- `0x18000f4bc`
- `0x18000f548`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18000f576`
- `RPCRT4!UuidCreate` at `0x18000f576`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f5ec`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f5ec`

## pseudocode

```c
void __fastcall CVolume::SetLocallyGeneratedVolId(CVolume *this)
{
  int v2; // edi
  RPC_STATUS v3; // eax
  bool v4; // zf
  signed int v5; // edi

  CVolume::RaiseIfWriteProtectedVolume(this);
  *((_DWORD *)this + 4) |= 2u;
  _InterlockedIncrement((volatile signed __int32 *)this + 142);
  v2 = 0;
  while ( 1 )
  {
    v3 = UuidCreate((UUID *)((char *)this + 264));
    v4 = ++v2 == 100;
    if ( v2 >= 100 )
      break;
    if ( v3 )
      goto LABEL_8;
    if ( (*((_BYTE *)this + 264) & 1) == 0 )
    {
      v4 = v2 == 100;
      break;
    }
  }
  if ( v4 )
    v3 = -2147417802;
LABEL_8:
  _InterlockedIncrement((volatile signed __int32 *)this + 142);
  if ( v3 )
    TrkRaiseWin32Error(v3);
  v5 = SetVolId((PCWSTR)this + 30, (CVolume *)((char *)this + 264));
  CEntropyRecorder::Put((struct CTrkWksSvc *)((char *)g_ptrkwks + 48));
  if ( v5 < 0 )
  {
    RaiseException(v5, 0, 0, 0);
    JUMPOUT(0x18000F5F2LL);
  }
  CVolume::MarkForMakeAllOidsReborn(this);
}

```

## disassembly

```asm
0x18000f548  mov     [rsp+arg_0], rbx
0x18000f54d  mov     [rsp+arg_8], rsi
0x18000f552  push    rdi
0x18000f553  sub     rsp, 20h
0x18000f557  mov     rbx, rcx
0x18000f55a  call    ?RaiseIfWriteProtectedVolume@CVolume@@AEBAXXZ; CVolume::RaiseIfWriteProtectedVolume(void)
0x18000f55f  or      dword ptr [rbx+10h], 2
0x18000f563  lock inc dword ptr [rbx+238h]
0x18000f56a  lea     rsi, [rbx+108h]
0x18000f571  xor     edi, edi
0x18000f573  mov     rcx, rsi; Uuid
0x18000f576  call    cs:__imp_UuidCreate
0x18000f57c  inc     edi
0x18000f57e  cmp     edi, 64h ; 'd'
0x18000f581  jge     short loc_18000F58F
0x18000f583  test    eax, eax
0x18000f585  jnz     short loc_18000F596
0x18000f587  test    byte ptr [rsi], 1
0x18000f58a  jnz     short loc_18000F573
0x18000f58c  cmp     edi, 64h ; 'd'
0x18000f58f  jnz     short loc_18000F596
0x18000f591  mov     eax, 80010136h
0x18000f596  lock inc dword ptr [rbx+238h]
0x18000f59d  test    eax, eax
0x18000f59f  jz      short loc_18000F5A9
0x18000f5a1  mov     ecx, eax; int
0x18000f5a3  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x18000f5a9  lea     rcx, [rbx+3Ch]; DosPathName
0x18000f5ad  mov     rdx, rsi; struct CVolumeId *
0x18000f5b0  call    ?SetVolId@@YAJPEBGAEBUCVolumeId@@@Z; SetVolId(ushort const *,CVolumeId const &)
0x18000f5b5  mov     rcx, cs:?g_ptrkwks@@3PEAVCTrkWksSvc@@EA; CTrkWksSvc * g_ptrkwks
0x18000f5bc  mov     edi, eax
0x18000f5be  add     rcx, 30h ; '0'; this
0x18000f5c2  call    ?Put@CEntropyRecorder@@QEAAXXZ; CEntropyRecorder::Put(void)
0x18000f5c7  test    edi, edi
0x18000f5c9  js      short loc_18000F5E2
0x18000f5cb  mov     rcx, rbx; this
0x18000f5ce  mov     rbx, [rsp+28h+arg_0]
0x18000f5d3  mov     rsi, [rsp+28h+arg_8]
0x18000f5d8  add     rsp, 20h
0x18000f5dc  pop     rdi
0x18000f5dd  jmp     ?MarkForMakeAllOidsReborn@CVolume@@QEAAXXZ; CVolume::MarkForMakeAllOidsReborn(void)
0x18000f5e2  xor     r9d, r9d; lpArguments
0x18000f5e5  xor     r8d, r8d; nNumberOfArguments
0x18000f5e8  xor     edx, edx; dwExceptionFlags
0x18000f5ea  mov     ecx, edi; dwExceptionCode
0x18000f5ec  call    cs:__imp_RaiseException
```
