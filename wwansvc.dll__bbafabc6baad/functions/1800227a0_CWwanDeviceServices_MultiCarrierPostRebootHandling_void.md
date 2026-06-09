# CWwanDeviceServices::MultiCarrierPostRebootHandling(void)

- ea: `0x1800227a0`
- end: `0x1800228f1`
- name: `?MultiCarrierPostRebootHandling@CWwanDeviceServices@@QEAAKXZ`
- size: `337`
- prototype: `unsigned int __fastcall(CWwanDeviceServices *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800616e0`

## callees

- `0x180012300`
- `0x180014f1c`
- `0x18001d640`
- `0x1800227a0`
- `0x1800769a4`

## import_xrefs

- `MobileNetworking!StopTimer` at `0x180022813`
- `MobileNetworking!StopTimer` at `0x180022813`
- `MobileNetworking!AcquireWriteLock` at `0x180022803`
- `MobileNetworking!AcquireWriteLock` at `0x180022803`
- `MobileNetworking!ReleaseWriteLock` at `0x18002282c`
- `MobileNetworking!ReleaseWriteLock` at `0x18002282c`

## string_xrefs

- `0x1800227bb`: `CWwanDeviceServices::MultiCarrierPostRebootHandling`
- `0x1800228d2`: ` MultiCarrierPostRebootHandling completed %x`

## pseudocode

```c
__int64 __fastcall CWwanDeviceServices::MultiCarrierPostRebootHandling(CWwanDeviceServices *this)
{
  int v2; // edx
  unsigned int v3; // eax
  unsigned int v4; // ebx
  _OWORD *v6; // [rsp+20h] [rbp-59h]
  __int64 v7; // [rsp+28h] [rbp-51h]
  _OWORD v8[2]; // [rsp+80h] [rbp+7h] BYREF
  __int64 v9; // [rsp+A0h] [rbp+27h]
  int v10; // [rsp+E0h] [rbp+67h] BYREF

  WwanLog::Info("CWwanDeviceServices::MultiCarrierPostRebootHandling", 0, L" MultiCarrierPostRebootHandling Invoked");
  v2 = *((_DWORD *)this + 169);
  *((_DWORD *)this + 169) = v2 & 0xFFFFFFFB;
  if ( (v2 & 4) != 0 )
  {
    AcquireWriteLock(
      *((_QWORD *)this + 86),
      (char *)this + 696,
      "CWwanDeviceServices::MultiCarrierPostRebootHandling",
      2888);
    StopTimer(*((_QWORD *)this + 86), "CWwanDeviceServices::MultiCarrierPostRebootHandling");
    ReleaseWriteLock(
      *((_QWORD *)this + 86),
      (char *)this + 696,
      "CWwanDeviceServices::MultiCarrierPostRebootHandling",
      2892);
  }
  CWwanManager::GetInstance();
  v10 = -1;
  v8[0] = 0u;
  LODWORD(v7) = 4;
  v6 = v8;
  v8[1] = 1u;
  v9 = 0;
  v3 = WwanTxmSendReqFromSource(this, 0, 2);
  v4 = v3;
  if ( v3 )
    WwanLog::Error(
      "CWwanDeviceServices::MultiCarrierPostRebootHandling",
      0,
      L"MultiCarrierPostRebootHandling WwanTxmSendReq()=0x%x FAILED",
      v3,
      v8,
      4,
      &v10,
      0,
      -1);
  WwanLog::Info(
    "CWwanDeviceServices::MultiCarrierPostRebootHandling",
    0,
    L" MultiCarrierPostRebootHandling completed %x",
    v4,
    v6,
    v7);
  return v4;
}

```

## disassembly

```asm
0x1800227a0  push    rbp
0x1800227a2  push    rbx
0x1800227a3  push    rsi
0x1800227a4  push    rdi
0x1800227a5  lea     rbp, [rsp-3Fh]
0x1800227aa  sub     rsp, 0B8h
0x1800227b1  mov     rdi, rcx
0x1800227b4  mov     dword ptr [rbp+57h+var_60+4], 0
0x1800227bb  lea     rsi, aCwwandeviceser_26; "CWwanDeviceServices::MultiCarrierPostRe"...
0x1800227c2  xor     edx, edx; struct _GUID *
0x1800227c4  mov     rcx, rsi; char *
0x1800227c7  lea     r8, aMulticarrierpo_1; " MultiCarrierPostRebootHandling Invoked"
0x1800227ce  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800227d3  mov     edx, [rdi+2A4h]
0x1800227d9  mov     eax, edx
0x1800227db  and     eax, 0FFFFFFFBh
0x1800227de  mov     [rdi+2A4h], eax
0x1800227e4  test    dl, 4
0x1800227e7  jz      short loc_180022832
0x1800227e9  mov     rcx, [rdi+2B0h]
0x1800227f0  lea     rbx, [rdi+2B8h]
0x1800227f7  mov     rdx, rbx
0x1800227fa  mov     r9d, 0B48h
0x180022800  mov     r8, rsi
0x180022803  call    cs:__imp_AcquireWriteLock
0x180022809  mov     rcx, [rdi+2B0h]
0x180022810  mov     rdx, rsi
0x180022813  call    cs:__imp_StopTimer
0x180022819  mov     rcx, [rdi+2B0h]
0x180022820  mov     r9d, 0B4Ch
0x180022826  mov     r8, rsi
0x180022829  mov     rdx, rbx
0x18002282c  call    cs:__imp_ReleaseWriteLock
0x180022832  call    ?GetInstance@CWwanManager@@SAPEAV1@XZ; CWwanManager::GetInstance(void)
0x180022837  or      eax, 0FFFFFFFFh
0x18002283a  mov     qword ptr [rbp+57h+var_80], 0
0x180022842  mov     [rsp+0D0h+var_90], eax
0x180022846  mov     r9d, 1
0x18002284c  mov     [rbp+57h+arg_0], eax
0x18002284f  xor     edx, edx
0x180022851  mov     [rsp+0D0h+var_98], 0
0x18002285a  lea     rax, [rbp+57h+arg_0]
0x18002285e  mov     [rsp+0D0h+var_A0], rax
0x180022863  mov     rcx, rdi
0x180022866  mov     qword ptr [rbp+57h+var_70], r9
0x18002286a  lea     rax, [rbp+57h+var_50]
0x18002286e  mov     qword ptr [rbp+57h+var_80+8], 0
0x180022876  lea     r8d, [r9+1]
0x18002287a  movups  xmm0, [rbp+57h+var_80]
0x18002287e  mov     qword ptr [rbp+57h+var_70+8], 0
0x180022886  movups  xmm1, [rbp+57h+var_70]
0x18002288a  mov     dword ptr [rbp+57h+var_60], 0
0x180022891  movaps  [rbp+57h+var_50], xmm0
0x180022895  movsd   xmm0, [rbp+57h+var_60]
0x18002289a  mov     dword ptr [rsp+0D0h+var_A8], 4
0x1800228a2  mov     [rsp+0D0h+var_B0], rax
0x1800228a7  movaps  [rbp+57h+var_40], xmm1
0x1800228ab  movsd   [rbp+57h+var_30], xmm0
0x1800228b0  call    ?WwanTxmSendReqFromSource@@YAKPEAU_GUID@@PEAXW4WWAN_EVENT_CODE@@W4WWAN_SETQUERY_TYPE@@UWWAN_API_INFO@@KPEBXPEAPEAXK@Z; WwanTxmSendReqFromSource(_GUID *,void *,WWAN_EVENT_CODE,WWAN_SETQUERY_TYPE,WWAN_API_INFO,ulong,void const *,void * *,ulong)
0x1800228b5  mov     ebx, eax
0x1800228b7  test    eax, eax
0x1800228b9  jz      short loc_1800228CF
0x1800228bb  mov     r9d, eax
0x1800228be  lea     r8, aMulticarrierpo_0; "MultiCarrierPostRebootHandling WwanTxmS"...
0x1800228c5  xor     edx, edx; struct _GUID *
0x1800228c7  mov     rcx, rsi; char *
0x1800228ca  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800228cf  mov     r9d, ebx
0x1800228d2  lea     r8, aMulticarrierpo; " MultiCarrierPostRebootHandling complet"...
0x1800228d9  xor     edx, edx; struct _GUID *
0x1800228db  mov     rcx, rsi; char *
0x1800228de  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800228e3  mov     eax, ebx
0x1800228e5  add     rsp, 0B8h
0x1800228ec  pop     rdi
0x1800228ed  pop     rsi
0x1800228ee  pop     rbx
0x1800228ef  pop     rbp
0x1800228f0  retn
```
