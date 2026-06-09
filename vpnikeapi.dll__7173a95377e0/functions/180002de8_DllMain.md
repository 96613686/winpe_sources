# DllMain

- ea: `0x180002de8`
- end: `0x180002f75`
- name: `DllMain`
- size: `397`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800019e4`

## callees

- `0x180002de8`
- `0x1800063a0`
- `0x180006598`
- `0x180006620`
- `0x180006854`
- `0x18000688c`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x180002f48`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x180002f48`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180002e03`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180002e03`
- `RPCRT4!RpcBindingFree` at `0x180002ea8`
- `RPCRT4!RpcBindingFree` at `0x180002ea8`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  PVOID *v3; // rbx
  TRACEHANDLE v4; // rcx

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      DisableThreadLibraryCalls(hinstDLL);
      if ( (int)McGenEventRegister_EventRegister() >= 0 )
        SetLibParams();
      qword_1800167E8 = 0;
      WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_VpnIkeApi;
      WPP_GLOBAL_Control = &WPP_MAIN_CB;
      WPP_MAIN_CB = 0;
      qword_1800167F0 = 1;
      WppInitUm();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 71);
      }
    }
  }
  else
  {
    if ( Binding )
    {
      RpcBindingFree(&Binding);
      Binding = 0;
    }
    *(_OWORD *)&gVpnIkeRpcTracingDesc = 0;
    gVpnIkeRpcEtwContext = 0;
    xmmword_180016830 = 0;
    gVpnIkeRpcTemplateFunc = 0;
    xmmword_180016840 = 0;
    xmmword_180016850 = 0;
    if ( MICROSOFT_WINDOWS_RRAS_PROVIDER_Context )
      McGenEventUnregister_EventUnregister(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, *(_QWORD *)&fdwReason, lpvReserved);
    v3 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 72);
        v3 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v3 != &WPP_GLOBAL_Control )
      {
        while ( v3 )
        {
          v4 = (TRACEHANDLE)v3[1];
          if ( v4 )
          {
            UnregisterTraceGuids(v4);
            v3[1] = 0;
          }
          v3 = (PVOID *)*v3;
        }
        WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180002de8  mov     [rsp+arg_0], rbx
0x180002ded  push    rdi
0x180002dee  sub     rsp, 20h
0x180002df2  test    edx, edx
0x180002df4  jz      loc_180002E97
0x180002dfa  cmp     edx, 1
0x180002dfd  jnz     loc_180002F65
0x180002e03  call    cs:__imp_DisableThreadLibraryCalls
0x180002e09  call    McGenEventRegister_EventRegister
0x180002e0e  test    eax, eax
0x180002e10  js      short loc_180002E17
0x180002e12  call    ?SetLibParams@@YAXXZ; SetLibParams(void)
0x180002e17  lea     rax, WPP_ThisDir_CTLGUID_VpnIkeApi
0x180002e1e  mov     cs:qword_1800167E8, 0
0x180002e29  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180002e30  lea     rax, WPP_MAIN_CB
0x180002e37  mov     cs:WPP_GLOBAL_Control, rax
0x180002e3e  mov     cs:WPP_MAIN_CB, 0
0x180002e49  mov     cs:qword_1800167F0, 1
0x180002e54  call    WppInitUm
0x180002e59  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e60  lea     rdi, WPP_GLOBAL_Control
0x180002e67  cmp     rcx, rdi
0x180002e6a  jz      loc_180002F65
0x180002e70  test    byte ptr [rcx+1Ch], 1
0x180002e74  jz      loc_180002F65
0x180002e7a  cmp     byte ptr [rcx+19h], 5
0x180002e7e  jb      loc_180002F65
0x180002e84  mov     rcx, [rcx+10h]
0x180002e88  mov     edx, 47h ; 'G'
0x180002e8d  call    WPP_SF_
0x180002e92  jmp     loc_180002F65
0x180002e97  cmp     cs:Binding, 0
0x180002e9f  jz      short loc_180002EB9
0x180002ea1  lea     rcx, Binding; Binding
0x180002ea8  call    cs:__imp_RpcBindingFree
0x180002eae  mov     cs:Binding, 0
0x180002eb9  cmp     cs:MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, 0
0x180002ec1  xorps   xmm0, xmm0
0x180002ec4  movups  cs:?gVpnIkeRpcTracingDesc@@3PAPEAU_EVENT_DESCRIPTOR@@A, xmm0; _EVENT_DESCRIPTOR * near * gVpnIkeRpcTracingDesc
0x180002ecb  mov     cs:?gVpnIkeRpcEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA, 0; _MCGEN_TRACE_CONTEXT * gVpnIkeRpcEtwContext
0x180002ed6  movups  cs:xmmword_180016830, xmm0
0x180002edd  mov     cs:?gVpnIkeRpcTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA, 0; ulong (*gVpnIkeRpcTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180002ee8  movups  cs:xmmword_180016840, xmm0
0x180002eef  movups  cs:xmmword_180016850, xmm0
0x180002ef6  jz      short loc_180002F04
0x180002ef8  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180002eff  call    McGenEventUnregister_EventUnregister
0x180002f04  mov     rbx, cs:WPP_GLOBAL_Control
0x180002f0b  lea     rdi, WPP_GLOBAL_Control
0x180002f12  cmp     rbx, rdi
0x180002f15  jz      short loc_180002F65
0x180002f17  test    byte ptr [rbx+1Ch], 1
0x180002f1b  jz      short loc_180002F38
0x180002f1d  cmp     byte ptr [rbx+19h], 5
0x180002f21  jb      short loc_180002F38
0x180002f23  mov     rcx, [rbx+10h]
0x180002f27  mov     edx, 48h ; 'H'
0x180002f2c  call    WPP_SF_
0x180002f31  mov     rbx, cs:WPP_GLOBAL_Control
0x180002f38  cmp     rbx, rdi
0x180002f3b  jz      short loc_180002F65
0x180002f3d  jmp     short loc_180002F59
0x180002f3f  mov     rcx, [rbx+8]; RegistrationHandle
0x180002f43  test    rcx, rcx
0x180002f46  jz      short loc_180002F56
0x180002f48  call    cs:__imp_UnregisterTraceGuids
0x180002f4e  mov     qword ptr [rbx+8], 0
0x180002f56  mov     rbx, [rbx]
0x180002f59  test    rbx, rbx
0x180002f5c  jnz     short loc_180002F3F
0x180002f5e  mov     cs:WPP_GLOBAL_Control, rdi
0x180002f65  mov     rbx, [rsp+28h+arg_0]
0x180002f6a  mov     eax, 1
0x180002f6f  add     rsp, 20h
0x180002f73  pop     rdi
0x180002f74  retn
```
