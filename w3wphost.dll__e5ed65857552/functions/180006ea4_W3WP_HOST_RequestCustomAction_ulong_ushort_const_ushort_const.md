# W3WP_HOST::RequestCustomAction(ulong,ushort const *,ushort const *)

- ea: `0x180006ea4`
- end: `0x18000700d`
- name: `?RequestCustomAction@W3WP_HOST@@QEAAXKPEBG0@Z`
- size: `361`
- prototype: `void(W3WP_HOST *__hidden this, unsigned int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180007c80`

## callees

- `0x180002090`
- `0x1800069cc`
- `0x180006ea4`
- `0x18000ab38`
- `0x18000d2ca`
- `0x18000e010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180006ff5`
- `iisutil!PuDbgPrint` at `0x180006ff5`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180006f16`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180006f26`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180006f16`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180006f26`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180006f4f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180006f68`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180006f4f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180006f68`

## string_xrefs

- `0x180006fe3`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x180006eb5`: `IIS_Worker_Process_Map_Config_Path`

## pseudocode

```c
void __fastcall W3WP_HOST::RequestCustomAction(
        W3WP_HOST *this,
        int a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  W3WP_HOST *v7; // rdi
  W3WP_HOST_WORKITEM *v8; // rax
  W3WP_HOST_WORKITEM *v9; // rbx
  int v10; // edi
  W3WP_HOST *v11; // rcx

  if ( wcscmp_0(a3, L"IIS_Worker_Process_Map_Config_Path") )
  {
    v7 = g_pW3WPHost;
    v8 = (W3WP_HOST_WORKITEM *)operator new(0xA8u);
    v9 = v8;
    if ( v8 )
    {
      W3WP_HOST_WORKITEM::W3WP_HOST_WORKITEM(v8, 1);
      *((_QWORD *)v9 + 5) = 0;
      *(_QWORD *)v9 = &RSCA_WORKITEM::`vftable';
      *((_DWORD *)v9 + 12) = 0;
      STRU::STRU((W3WP_HOST_WORKITEM *)((char *)v9 + 56));
      STRU::STRU((W3WP_HOST_WORKITEM *)((char *)v9 + 112));
      (**(void (__fastcall ***)(W3WP_HOST *))v7)(v7);
      *((_QWORD *)v9 + 5) = v7;
      *((_DWORD *)v9 + 12) = a2;
      v10 = STRU::Copy((W3WP_HOST_WORKITEM *)((char *)v9 + 56), a3);
      if ( v10 < 0 || (v10 = STRU::Copy((W3WP_HOST_WORKITEM *)((char *)v9 + 112), a4), v10 < 0) )
      {
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v9 + 5) + 8LL))(*((_QWORD *)v9 + 5));
        *((_QWORD *)v9 + 5) = 0;
      }
      else
      {
        v10 = W3WP_HOST::QueueWorkItem(v11, v9);
        if ( v10 >= 0 )
          return;
      }
      (**(void (__fastcall ***)(W3WP_HOST_WORKITEM *, __int64))v9)(v9, 1);
    }
    else
    {
      v10 = -2147024882;
    }
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
        3869,
        "W3WP_HOST::RequestCustomAction",
        "CustomAction call %S failed with error 0x%x \n",
        a3,
        v10);
  }
}

```

## disassembly

```asm
0x180006ea4  push    rbx
0x180006ea6  push    rbp
0x180006ea7  push    rsi
0x180006ea8  push    rdi
0x180006ea9  push    r14
0x180006eab  sub     rsp, 40h
0x180006eaf  mov     r14d, edx
0x180006eb2  mov     rcx, r8; String1
0x180006eb5  lea     rdx, aIisWorkerProce; "IIS_Worker_Process_Map_Config_Path"
0x180006ebc  mov     rbp, r9
0x180006ebf  mov     rsi, r8
0x180006ec2  call    wcscmp_0
0x180006ec7  test    eax, eax
0x180006ec9  jz      loc_180007001
0x180006ecf  mov     rdi, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x180006ed6  mov     ecx, 0A8h; Size
0x180006edb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006ee0  mov     rbx, rax
0x180006ee3  test    rax, rax
0x180006ee6  jz      loc_180006FB7
0x180006eec  mov     edx, 1; int
0x180006ef1  mov     rcx, rax; this
0x180006ef4  call    ??0W3WP_HOST_WORKITEM@@QEAA@H@Z; W3WP_HOST_WORKITEM::W3WP_HOST_WORKITEM(int)
0x180006ef9  lea     rcx, ??_7RSCA_WORKITEM@@6B@; const RSCA_WORKITEM::`vftable'
0x180006f00  mov     qword ptr [rbx+28h], 0
0x180006f08  mov     [rbx], rcx
0x180006f0b  lea     rcx, [rbx+38h]
0x180006f0f  mov     dword ptr [rbx+30h], 0
0x180006f16  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180006f1d  nop     dword ptr [rax+rax+00h]
0x180006f22  lea     rcx, [rbx+70h]
0x180006f26  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180006f2d  nop     dword ptr [rax+rax+00h]
0x180006f32  mov     rax, [rdi]
0x180006f35  mov     rcx, rdi
0x180006f38  mov     rax, [rax]
0x180006f3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f40  lea     rcx, [rbx+38h]
0x180006f44  mov     [rbx+28h], rdi
0x180006f48  mov     rdx, rsi
0x180006f4b  mov     [rbx+30h], r14d
0x180006f4f  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180006f56  nop     dword ptr [rax+rax+00h]
0x180006f5b  mov     edi, eax
0x180006f5d  test    eax, eax
0x180006f5f  js      short loc_180006F8A
0x180006f61  lea     rcx, [rbx+70h]
0x180006f65  mov     rdx, rbp
0x180006f68  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180006f6f  nop     dword ptr [rax+rax+00h]
0x180006f74  mov     edi, eax
0x180006f76  test    eax, eax
0x180006f78  js      short loc_180006F8A
0x180006f7a  mov     rdx, rbx; struct W3WP_HOST_WORKITEM *
0x180006f7d  call    ?QueueWorkItem@W3WP_HOST@@QEAAJPEAVW3WP_HOST_WORKITEM@@@Z; W3WP_HOST::QueueWorkItem(W3WP_HOST_WORKITEM *)
0x180006f82  mov     edi, eax
0x180006f84  test    eax, eax
0x180006f86  jns     short loc_180007001
0x180006f88  jmp     short loc_180006FA2
0x180006f8a  mov     rcx, [rbx+28h]
0x180006f8e  mov     rax, [rcx]
0x180006f91  mov     rax, [rax+8]
0x180006f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f9a  mov     qword ptr [rbx+28h], 0
0x180006fa2  mov     rax, [rbx]
0x180006fa5  mov     edx, 1
0x180006faa  mov     rcx, rbx
0x180006fad  mov     rax, [rax]
0x180006fb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fb5  jmp     short loc_180006FBC
0x180006fb7  mov     edi, 8007000Eh
0x180006fbc  test    byte ptr cs:g_dwDebugFlags, 3
0x180006fc3  jz      short loc_180007001
0x180006fc5  mov     rcx, cs:g_pDebug
0x180006fcc  lea     rax, aCustomactionCa; "CustomAction call %S failed with error "...
0x180006fd3  mov     [rsp+68h+var_38], edi
0x180006fd7  lea     r9, aW3wpHostReques; "W3WP_HOST::RequestCustomAction"
0x180006fde  mov     [rsp+68h+var_40], rsi
0x180006fe3  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180006fea  mov     r8d, 0F1Dh
0x180006ff0  mov     [rsp+68h+var_48], rax
0x180006ff5  call    cs:__imp_PuDbgPrint
0x180006ffc  nop     dword ptr [rax+rax+00h]
0x180007001  add     rsp, 40h
0x180007005  pop     r14
0x180007007  pop     rdi
0x180007008  pop     rsi
0x180007009  pop     rbp
0x18000700a  pop     rbx
0x18000700b  retn
```
