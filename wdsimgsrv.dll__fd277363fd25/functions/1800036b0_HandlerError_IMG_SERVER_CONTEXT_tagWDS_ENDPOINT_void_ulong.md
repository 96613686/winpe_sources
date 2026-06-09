# HandlerError(_IMG_SERVER_CONTEXT *,tagWDS_ENDPOINT *,void *,ulong)

- ea: `0x1800036b0`
- end: `0x180003832`
- name: `?HandlerError@@YAKPEAU_IMG_SERVER_CONTEXT@@PEAUtagWDS_ENDPOINT@@PEAXK@Z`
- size: `386`
- prototype: `unsigned int __fastcall(struct _IMG_SERVER_CONTEXT *, struct tagWDS_ENDPOINT *, void *, unsigned int)`
- caller_count: `7`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002a0c`
- `0x180002e64`
- `0x180003af4`
- `0x180003dc4`
- `0x180006020`
- `0x180006548`
- `0x180006e50`

## callees

- `0x1800036b0`
- `0x180007eb4`
- `0x180007fd8`
- `0x18000b370`
- `0x18000fdf8`
- `0x180016020`

## import_xrefs

- `WDSSRV!WdsSendReply` at `0x1800037b1`
- `WDSSRV!WdsSendReply` at `0x1800037b1`
- `WDSSRV!WdsPacketFree` at `0x1800037de`
- `WDSSRV!WdsPacketFree` at `0x1800037de`
- `WDSCSL!WdsCpPacketGetBuffer` at `0x180003780`
- `WDSCSL!WdsCpPacketGetBuffer` at `0x180003780`
- `WDSCSL!WdsCpPacketRelease` at `0x1800037f3`
- `WDSCSL!WdsCpPacketRelease` at `0x1800037f3`
- `WDSCSL!WdsCpPacketInitialize` at `0x180003718`
- `WDSCSL!WdsCpPacketInitialize` at `0x180003718`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x180003764`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x180003764`

## pseudocode

```c
__int64 __fastcall HandlerError(struct _IMG_SERVER_CONTEXT *a1, struct tagWDS_ENDPOINT *a2, void *a3, int a4)
{
  __int64 Buffer; // rbx
  __int64 v7; // rdx
  __int64 v8; // r8
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // r8
  unsigned int v17; // [rsp+30h] [rbp-30h] BYREF
  void *v18; // [rsp+38h] [rbp-28h] BYREF
  __int64 v19; // [rsp+40h] [rbp-20h] BYREF
  __int64 v20; // [rsp+48h] [rbp-18h] BYREF
  int v21; // [rsp+50h] [rbp-10h]

  v18 = 0;
  v19 = 0;
  v17 = 0;
  WdsImgTrace(0x10000u, L"-> HandlerError");
  v20 = 0x20000000CLL;
  v21 = a4;
  Buffer = (unsigned int)WdsCpPacketInitialize(g_hProvider, &v20, &v18);
  if ( !(unsigned int)ElValidateWin32(Buffer, v7, v8, 2533) )
  {
    v9 = WdsCliAddVarUlong(v18, L"VERSION", 1);
    if ( (int)ElValidateHr(v9, v10, v11, 2536) >= 0 )
    {
      Buffer = (unsigned int)WdsCpPacketGetBuffer(v18, &v19, &v17);
      if ( !(unsigned int)ElValidateWin32(Buffer, v12, v13, 2543) )
      {
        Buffer = (unsigned int)WdsSendReply(a3, v19, v17, 0, 0);
        ElValidateWin32(Buffer, v14, v15, 2551);
      }
    }
    else
    {
      LODWORD(Buffer) = WIN32_FROM_HRESULT(v9);
    }
  }
  if ( v19 )
    WdsPacketFree(g_hProvider, 0);
  if ( v18 )
    WdsCpPacketRelease();
  WdsImgTrace(0x10000u, L"<- HandlerError=%x", (unsigned int)Buffer);
  return (unsigned int)Buffer;
}

```

## disassembly

```asm
0x1800036b0  mov     [rsp-8+arg_0], rbx
0x1800036b5  mov     [rsp-8+arg_8], rdi
0x1800036ba  push    rbp
0x1800036bb  mov     rbp, rsp
0x1800036be  sub     rsp, 60h
0x1800036c2  mov     rax, cs:__security_cookie
0x1800036c9  xor     rax, rsp
0x1800036cc  mov     [rbp+var_8], rax
0x1800036d0  xor     eax, eax
0x1800036d2  lea     rdx, aHandlererror; "-> HandlerError"
0x1800036d9  and     [rbp+var_28], rax
0x1800036dd  mov     ecx, 10000h; unsigned int
0x1800036e2  and     [rbp+var_20], rax
0x1800036e6  mov     ebx, r9d
0x1800036e9  and     [rbp+var_30], eax
0x1800036ec  mov     rdi, r8
0x1800036ef  mov     [rbp+var_18], rax
0x1800036f3  mov     [rbp+var_10], eax
0x1800036f6  call    ?WdsImgTrace@@YAKKPEBGZZ; WdsImgTrace(ulong,ushort const *,...)
0x1800036fb  mov     rcx, cs:?g_hProvider@@3PEAXEA; void * g_hProvider
0x180003702  lea     r8, [rbp+var_28]
0x180003706  lea     rdx, [rbp+var_18]
0x18000370a  mov     dword ptr [rbp+var_18], 0Ch
0x180003711  mov     byte ptr [rbp+var_18+4], 2
0x180003715  mov     [rbp+var_10], ebx
0x180003718  call    cs:__imp_WdsCpPacketInitialize
0x18000371f  nop     dword ptr [rax+rax+00h]
0x180003724  mov     ecx, eax
0x180003726  mov     r9d, 9E5h
0x18000372c  mov     ebx, eax
0x18000372e  call    ElValidateWin32
0x180003733  test    eax, eax
0x180003735  jnz     loc_1800037CC
0x18000373b  mov     rcx, [rbp+var_28]; void *
0x18000373f  lea     r8d, [rax+1]; unsigned int
0x180003743  lea     rdx, aVersion_0; "VERSION"
0x18000374a  call    ?WdsCliAddVarUlong@@YAJPEAXPEAGK@Z; WdsCliAddVarUlong(void *,ushort *,ulong)
0x18000374f  mov     r9d, 9E8h
0x180003755  mov     ecx, eax
0x180003757  mov     ebx, eax
0x180003759  call    ElValidateHr
0x18000375e  test    eax, eax
0x180003760  jns     short loc_180003774
0x180003762  mov     ecx, ebx
0x180003764  call    cs:__imp_?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x18000376b  nop     dword ptr [rax+rax+00h]
0x180003770  mov     ebx, eax
0x180003772  jmp     short loc_1800037CC
0x180003774  mov     rcx, [rbp+var_28]
0x180003778  lea     r8, [rbp+var_30]
0x18000377c  lea     rdx, [rbp+var_20]
0x180003780  call    cs:__imp_WdsCpPacketGetBuffer
0x180003787  nop     dword ptr [rax+rax+00h]
0x18000378c  mov     ecx, eax
0x18000378e  mov     r9d, 9EFh
0x180003794  mov     ebx, eax
0x180003796  call    ElValidateWin32
0x18000379b  test    eax, eax
0x18000379d  jnz     short loc_1800037CC
0x18000379f  mov     r8d, [rbp+var_30]
0x1800037a3  xor     r9d, r9d
0x1800037a6  mov     rdx, [rbp+var_20]
0x1800037aa  mov     rcx, rdi
0x1800037ad  and     [rsp+60h+var_40], eax
0x1800037b1  call    cs:__imp_WdsSendReply
0x1800037b8  nop     dword ptr [rax+rax+00h]
0x1800037bd  mov     ecx, eax
0x1800037bf  mov     r9d, 9F7h
0x1800037c5  mov     ebx, eax
0x1800037c7  call    ElValidateWin32
0x1800037cc  mov     r8, [rbp+var_20]
0x1800037d0  test    r8, r8
0x1800037d3  jz      short loc_1800037EA
0x1800037d5  mov     rcx, cs:?g_hProvider@@3PEAXEA; void * g_hProvider
0x1800037dc  xor     edx, edx
0x1800037de  call    cs:__imp_WdsPacketFree
0x1800037e5  nop     dword ptr [rax+rax+00h]
0x1800037ea  mov     rcx, [rbp+var_28]
0x1800037ee  test    rcx, rcx
0x1800037f1  jz      short loc_1800037FF
0x1800037f3  call    cs:__imp_WdsCpPacketRelease
0x1800037fa  nop     dword ptr [rax+rax+00h]
0x1800037ff  mov     r8d, ebx
0x180003802  lea     rdx, aHandlererrorX; "<- HandlerError=%x"
0x180003809  mov     ecx, 10000h; unsigned int
0x18000380e  call    ?WdsImgTrace@@YAKKPEBGZZ; WdsImgTrace(ulong,ushort const *,...)
0x180003813  mov     eax, ebx
0x180003815  mov     rcx, [rbp+var_8]
0x180003819  xor     rcx, rsp; StackCookie
0x18000381c  call    __security_check_cookie
0x180003821  mov     rbx, [rsp+60h+arg_0]
0x180003826  mov     rdi, [rsp+60h+arg_8]
0x18000382b  add     rsp, 60h
0x18000382f  pop     rbp
0x180003830  retn
```
