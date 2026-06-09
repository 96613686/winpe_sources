# CRdrPnpManager::RpcGetInterfaceGuids(IRemoteDevice *,ulong *,_GUID * *)

- ea: `0x180027e3c`
- end: `0x180027fca`
- name: `?RpcGetInterfaceGuids@CRdrPnpManager@@QEAAJPEAUIRemoteDevice@@PEAKPEAPEAU_GUID@@@Z`
- size: `398`
- prototype: `__int64 __fastcall(CRdrPnpManager *__hidden this, struct IRemoteDevice *, unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180029d00`

## callees

- `0x18000b8f8`
- `0x18000b98c`
- `0x18000bd04`
- `0x18001ba64`
- `0x180027e3c`
- `0x180047ea6`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027fb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027fb2`

## pseudocode

```c
__int64 __fastcall CRdrPnpManager::RpcGetInterfaceGuids(
        CRdrPnpManager *this,
        struct IRemoteDevice *a2,
        unsigned int *a3,
        struct _GUID **a4)
{
  __int64 v4; // rax
  int v7; // ebx
  unsigned int v8; // eax
  unsigned int v9; // eax
  struct _GUID *v10; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  void *Src; // [rsp+40h] [rbp+8h] BYREF

  Src = this;
  v4 = *(_QWORD *)a2;
  Src = 0;
  v7 = (*(__int64 (__fastcall **)(struct IRemoteDevice *, void **))(v4 + 96))(a2, &Src);
  if ( v7 >= 0 )
  {
    if ( *a3 )
    {
      v10 = (struct _GUID *)operator new(16LL * *a3);
      *a4 = v10;
      if ( v10 )
      {
        memcpy_0(v10, Src, 16LL * *a3);
      }
      else
      {
        if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
          && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Ds(
            *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
            48,
            (unsigned int)WPP_94246e01360c359abb577584ca0bcde6_Traceguids,
            CurrentThreadActivityIdPrefix,
            (__int64)"GUID[]");
        }
        v7 = -2147024882;
      }
    }
    else
    {
      v7 = -2147418113;
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v9 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          47,
          (unsigned int)WPP_94246e01360c359abb577584ca0bcde6_Traceguids,
          v9,
          (__int64)"*pCount == 0",
          255);
      }
    }
  }
  else if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
         && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    v8 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      46,
      (unsigned int)WPP_94246e01360c359abb577584ca0bcde6_Traceguids,
      v8,
      (__int64)"pDevice->GetInterfaces FAILED",
      v7);
  }
  if ( Src )
    CoTaskMemFree(Src);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180027e3c  mov     r11, rsp
0x180027e3f  mov     [r11+10h], rbx
0x180027e43  mov     [r11+18h], rsi
0x180027e47  mov     [r11+8], rcx
0x180027e4b  push    rdi
0x180027e4c  sub     rsp, 30h
0x180027e50  mov     rax, [rdx]
0x180027e53  mov     rcx, rdx
0x180027e56  lea     rdx, [r11+8]
0x180027e5a  mov     qword ptr [r11+8], 0
0x180027e62  mov     rsi, r9
0x180027e65  mov     rdi, r8
0x180027e68  mov     rax, [rax+60h]
0x180027e6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e71  mov     ebx, eax
0x180027e73  test    eax, eax
0x180027e75  jns     short loc_180027EDB
0x180027e77  mov     rax, cs:WPP_GLOBAL_Control
0x180027e7e  lea     rcx, WPP_GLOBAL_Control
0x180027e85  cmp     rax, rcx
0x180027e88  jz      loc_180027FA8
0x180027e8e  test    byte ptr [rax+1Ch], 8
0x180027e92  jz      loc_180027FA8
0x180027e98  cmp     byte ptr [rax+19h], 2
0x180027e9c  jb      loc_180027FA8
0x180027ea2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180027ea7  mov     edx, 2Eh ; '.'
0x180027eac  mov     [rsp+38h+var_10], ebx
0x180027eb0  lea     rcx, aPdeviceGetinte; "pDevice->GetInterfaces FAILED"
0x180027eb7  mov     [rsp+38h+var_18], rcx
0x180027ebc  lea     r8, WPP_94246e01360c359abb577584ca0bcde6_Traceguids
0x180027ec3  mov     rcx, cs:WPP_GLOBAL_Control
0x180027eca  mov     r9d, eax
0x180027ecd  mov     rcx, [rcx+10h]
0x180027ed1  call    WPP_SF_DsD
0x180027ed6  jmp     loc_180027FA8
0x180027edb  cmp     dword ptr [rdi], 0
0x180027ede  jnz     short loc_180027F2B
0x180027ee0  mov     ebx, 8000FFFFh
0x180027ee5  mov     rax, cs:WPP_GLOBAL_Control
0x180027eec  lea     rcx, WPP_GLOBAL_Control
0x180027ef3  cmp     rax, rcx
0x180027ef6  jz      loc_180027FA8
0x180027efc  test    byte ptr [rax+1Ch], 8
0x180027f00  jz      loc_180027FA8
0x180027f06  cmp     byte ptr [rax+19h], 2
0x180027f0a  jb      loc_180027FA8
0x180027f10  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180027f15  mov     edx, 2Fh ; '/'
0x180027f1a  mov     [rsp+38h+var_10], 8000FFFFh
0x180027f22  lea     rcx, aPcount0; "*pCount == 0"
0x180027f29  jmp     short loc_180027EB7
0x180027f2b  mov     ecx, [rdi]
0x180027f2d  shl     rcx, 4; Size
0x180027f31  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180027f36  mov     [rsi], rax
0x180027f39  test    rax, rax
0x180027f3c  jnz     short loc_180027F94
0x180027f3e  mov     rax, cs:WPP_GLOBAL_Control
0x180027f45  lea     rcx, WPP_GLOBAL_Control
0x180027f4c  cmp     rax, rcx
0x180027f4f  jz      short loc_180027F8D
0x180027f51  test    byte ptr [rax+1Ch], 8
0x180027f55  jz      short loc_180027F8D
0x180027f57  cmp     byte ptr [rax+19h], 2
0x180027f5b  jb      short loc_180027F8D
0x180027f5d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180027f62  lea     rcx, aGuid; "GUID[]"
0x180027f69  mov     edx, 30h ; '0'
0x180027f6e  mov     [rsp+38h+var_18], rcx
0x180027f73  lea     r8, WPP_94246e01360c359abb577584ca0bcde6_Traceguids
0x180027f7a  mov     rcx, cs:WPP_GLOBAL_Control
0x180027f81  mov     r9d, eax
0x180027f84  mov     rcx, [rcx+10h]
0x180027f88  call    WPP_SF_Ds
0x180027f8d  mov     ebx, 8007000Eh
0x180027f92  jmp     short loc_180027FA8
0x180027f94  mov     r8d, [rdi]
0x180027f97  mov     rcx, rax; void *
0x180027f9a  mov     rdx, [rsp+38h+Src]; Src
0x180027f9f  shl     r8, 4; Size
0x180027fa3  call    memcpy_0
0x180027fa8  mov     rcx, [rsp+38h+Src]; pv
0x180027fad  test    rcx, rcx
0x180027fb0  jz      short loc_180027FB8
0x180027fb2  call    cs:__imp_CoTaskMemFree
0x180027fb8  mov     rsi, [rsp+38h+arg_10]
0x180027fbd  mov     eax, ebx
0x180027fbf  mov     rbx, [rsp+38h+arg_8]
0x180027fc4  add     rsp, 30h
0x180027fc8  pop     rdi
0x180027fc9  retn
```
