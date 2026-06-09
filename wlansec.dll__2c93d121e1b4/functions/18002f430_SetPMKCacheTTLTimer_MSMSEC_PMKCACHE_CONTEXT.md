# SetPMKCacheTTLTimer(MSMSEC_PMKCACHE_CONTEXT *)

- ea: `0x18002f430`
- end: `0x18002f61d`
- name: `?SetPMKCacheTTLTimer@@YAKPEAUMSMSEC_PMKCACHE_CONTEXT@@@Z`
- size: `493`
- prototype: `unsigned int __fastcall(struct MSMSEC_PMKCACHE_CONTEXT *)`
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x18002ec3c`
- `0x18003e5bc`
- `0x18006b550`

## callees

- `0x18000431c`
- `0x18000892c`
- `0x180008998`
- `0x1800089dc`
- `0x18001af40`
- `0x18001b2b0`
- `0x18002f430`
- `0x18002f624`

## import_xrefs

- `MobileNetworking!DiffTimeInMSec` at `0x18002f55e`
- `MobileNetworking!DiffTimeInMSec` at `0x18002f55e`

## string_xrefs

- `0x18002f49f`: `SetPMKCacheTTLTimer`
- `0x18002f59a`: `SetPMKCacheTTLTimer`

## pseudocode

```c
__int64 __fastcall SetPMKCacheTTLTimer(struct MSMSEC_PMKCACHE_CONTEXT *a1)
{
  unsigned int NextExpiryTime; // eax
  unsigned int v3; // ebx
  PVOID *v4; // rcx
  unsigned __int64 Time; // rax
  PVOID *v6; // rcx
  unsigned int v7; // edi
  unsigned int v8; // eax
  unsigned int started; // eax
  unsigned __int64 v11; // [rsp+58h] [rbp+10h] BYREF

  v11 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 72, &WPP_33279517f8f53e554228e3ed86a1217c_Traceguids);
  NextExpiryTime = GetNextExpiryTime(a1, &v11);
  v3 = NextExpiryTime;
  if ( NextExpiryTime != 1168 )
  {
    if ( NextExpiryTime )
    {
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v3;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_26;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        74,
        &WPP_33279517f8f53e554228e3ed86a1217c_Traceguids,
        NextExpiryTime);
    }
    else
    {
      Time = PmkCacheGetTime();
      if ( v11 >= Time + 100000 )
      {
        v8 = DiffTimeInMSec(v11, Time);
        v6 = (PVOID *)WPP_GLOBAL_Control;
        v7 = v8;
      }
      else
      {
        v6 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 75, &WPP_33279517f8f53e554228e3ed86a1217c_Traceguids);
          v6 = (PVOID *)WPP_GLOBAL_Control;
        }
        v7 = 2000;
      }
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 68) & 2) != 0 )
        WPP_SF_d(v6[7], 76, &WPP_33279517f8f53e554228e3ed86a1217c_Traceguids, v7);
      started = MSMSecStartTimer(*((void **)a1 + 28), (void *)8, v7, "SetPMKCacheTTLTimer");
      v3 = started;
      if ( started )
      {
        v4 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return v3;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          goto LABEL_26;
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          77,
          &WPP_33279517f8f53e554228e3ed86a1217c_Traceguids,
          v7,
          started);
      }
    }
    goto LABEL_25;
  }
  v3 = 0;
  MSMSecStopTimer(*((void **)a1 + 28), "SetPMKCacheTTLTimer");
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v3;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 73, &WPP_33279517f8f53e554228e3ed86a1217c_Traceguids);
LABEL_25:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_26:
  if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 17) & 0x100) != 0 )
    WPP_SF_d(v4[7], 78, &WPP_33279517f8f53e554228e3ed86a1217c_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x18002f430  mov     [rsp+arg_0], rbx
0x18002f435  mov     [rsp+arg_10], rbp
0x18002f43a  push    rsi
0x18002f43b  push    rdi
0x18002f43c  push    r14
0x18002f43e  sub     rsp, 30h
0x18002f442  mov     rsi, rcx
0x18002f445  mov     [rsp+48h+arg_8], 0
0x18002f44e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f455  lea     rbp, WPP_GLOBAL_Control
0x18002f45c  lea     r14, WPP_33279517f8f53e554228e3ed86a1217c_Traceguids
0x18002f463  cmp     rcx, rbp
0x18002f466  jz      short loc_18002F482
0x18002f468  test    dword ptr [rcx+44h], 100h
0x18002f46f  jz      short loc_18002F482
0x18002f471  mov     rcx, [rcx+38h]
0x18002f475  mov     edx, 48h ; 'H'
0x18002f47a  mov     r8, r14
0x18002f47d  call    WPP_SF_
0x18002f482  lea     rdx, [rsp+48h+arg_8]; unsigned __int64 *
0x18002f487  mov     rcx, rsi; struct MSMSEC_PMKCACHE_CONTEXT *
0x18002f48a  call    ?GetNextExpiryTime@@YAKPEAUMSMSEC_PMKCACHE_CONTEXT@@PEA_K@Z; GetNextExpiryTime(MSMSEC_PMKCACHE_CONTEXT *,unsigned __int64 *)
0x18002f48f  mov     ebx, eax
0x18002f491  cmp     eax, 490h
0x18002f496  jnz     short loc_18002F4DB
0x18002f498  mov     rcx, [rsi+0E0h]; void *
0x18002f49f  lea     rdx, aSetpmkcachettl; "SetPMKCacheTTLTimer"
0x18002f4a6  xor     ebx, ebx
0x18002f4a8  call    ?MSMSecStopTimer@@YAXPEAXPEBD@Z; MSMSecStopTimer(void *,char const *)
0x18002f4ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f4b4  cmp     rcx, rbp
0x18002f4b7  jz      loc_18002F607
0x18002f4bd  test    byte ptr [rcx+44h], 2
0x18002f4c1  jz      loc_18002F5E5
0x18002f4c7  mov     rcx, [rcx+38h]
0x18002f4cb  lea     edx, [rbx+49h]
0x18002f4ce  mov     r8, r14
0x18002f4d1  call    WPP_SF_
0x18002f4d6  jmp     loc_18002F5DE
0x18002f4db  test    eax, eax
0x18002f4dd  jz      short loc_18002F512
0x18002f4df  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f4e6  cmp     rcx, rbp
0x18002f4e9  jz      loc_18002F607
0x18002f4ef  test    byte ptr [rcx+44h], 1
0x18002f4f3  jz      loc_18002F5E5
0x18002f4f9  mov     rcx, [rcx+38h]
0x18002f4fd  mov     edx, 4Ah ; 'J'
0x18002f502  mov     r9d, eax
0x18002f505  mov     r8, r14
0x18002f508  call    WPP_SF_d
0x18002f50d  jmp     loc_18002F5DE
0x18002f512  call    ?PmkCacheGetTime@@YA_KXZ; PmkCacheGetTime(void)
0x18002f517  lea     rcx, [rax+186A0h]
0x18002f51e  cmp     [rsp+48h+arg_8], rcx
0x18002f523  jnb     short loc_18002F556
0x18002f525  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f52c  cmp     rcx, rbp
0x18002f52f  jz      short loc_18002F54F
0x18002f531  test    byte ptr [rcx+44h], 2
0x18002f535  jz      short loc_18002F54F
0x18002f537  mov     rcx, [rcx+38h]
0x18002f53b  mov     edx, 4Bh ; 'K'
0x18002f540  mov     r8, r14
0x18002f543  call    WPP_SF_
0x18002f548  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f54f  mov     edi, 7D0h
0x18002f554  jmp     short loc_18002F574
0x18002f556  mov     rcx, [rsp+48h+arg_8]
0x18002f55b  mov     rdx, rax
0x18002f55e  call    cs:__imp_DiffTimeInMSec
0x18002f565  nop     dword ptr [rax+rax+00h]
0x18002f56a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f571  mov     rdi, rax
0x18002f574  cmp     rcx, rbp
0x18002f577  jz      short loc_18002F593
0x18002f579  test    byte ptr [rcx+44h], 2
0x18002f57d  jz      short loc_18002F593
0x18002f57f  mov     rcx, [rcx+38h]
0x18002f583  mov     edx, 4Ch ; 'L'
0x18002f588  mov     r9d, edi
0x18002f58b  mov     r8, r14
0x18002f58e  call    WPP_SF_d
0x18002f593  mov     rcx, [rsi+0E0h]; void *
0x18002f59a  lea     r9, aSetpmkcachettl; "SetPMKCacheTTLTimer"
0x18002f5a1  mov     r8d, edi; unsigned int
0x18002f5a4  mov     edx, 8; void *
0x18002f5a9  call    ?MSMSecStartTimer@@YAKPEAX0KPEBD@Z; MSMSecStartTimer(void *,void *,ulong,char const *)
0x18002f5ae  mov     ebx, eax
0x18002f5b0  test    eax, eax
0x18002f5b2  jz      short loc_18002F5DE
0x18002f5b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f5bb  cmp     rcx, rbp
0x18002f5be  jz      short loc_18002F607
0x18002f5c0  test    byte ptr [rcx+44h], 1
0x18002f5c4  jz      short loc_18002F5E5
0x18002f5c6  mov     rcx, [rcx+38h]
0x18002f5ca  mov     edx, 4Dh ; 'M'
0x18002f5cf  mov     r9d, edi
0x18002f5d2  mov     [rsp+48h+var_28], eax
0x18002f5d6  mov     r8, r14
0x18002f5d9  call    WPP_SF_dd
0x18002f5de  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f5e5  cmp     rcx, rbp
0x18002f5e8  jz      short loc_18002F607
0x18002f5ea  test    dword ptr [rcx+44h], 100h
0x18002f5f1  jz      short loc_18002F607
0x18002f5f3  mov     rcx, [rcx+38h]
0x18002f5f7  mov     edx, 4Eh ; 'N'
0x18002f5fc  mov     r9d, ebx
0x18002f5ff  mov     r8, r14
0x18002f602  call    WPP_SF_d
0x18002f607  mov     rbp, [rsp+48h+arg_10]
0x18002f60c  mov     eax, ebx
0x18002f60e  mov     rbx, [rsp+48h+arg_0]
0x18002f613  add     rsp, 30h
0x18002f617  pop     r14
0x18002f619  pop     rdi
0x18002f61a  pop     rsi
0x18002f61b  retn
```
