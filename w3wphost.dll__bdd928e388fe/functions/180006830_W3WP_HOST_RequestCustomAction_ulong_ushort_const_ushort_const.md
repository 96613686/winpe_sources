# W3WP_HOST::RequestCustomAction(ulong,ushort const *,ushort const *)

- ea: `0x180006830`
- end: `0x18000697a`
- name: `?RequestCustomAction@W3WP_HOST@@QEAAXKPEBG0@Z`
- size: `330`
- prototype: `void __fastcall(W3WP_HOST *this, int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800074dc`

## callees

- `0x180001f68`
- `0x1800063a0`
- `0x180006830`
- `0x180009f38`
- `0x18000c3aa`
- `0x18000d010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180006969`
- `iisutil!PuDbgPrint` at `0x180006969`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800068a2`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800068ac`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800068a2`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800068ac`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800068cf`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800068e2`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800068cf`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800068e2`

## string_xrefs

- `0x180006957`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x180006841`: `IIS_Worker_Process_Map_Config_Path`

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
  W3WP_HOST *v10; // rcx

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
      if ( (int)STRU::Copy((W3WP_HOST_WORKITEM *)((char *)v9 + 56), a3) < 0
        || (int)STRU::Copy((W3WP_HOST_WORKITEM *)((char *)v9 + 112), a4) < 0 )
      {
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v9 + 5) + 8LL))(*((_QWORD *)v9 + 5));
        *((_QWORD *)v9 + 5) = 0;
      }
      else if ( (int)W3WP_HOST::QueueWorkItem(v10, v9) >= 0 )
      {
        return;
      }
      (**(void (__fastcall ***)(W3WP_HOST_WORKITEM *, __int64))v9)(v9, 1);
    }
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
        3869,
        "W3WP_HOST::RequestCustomAction",
        "CustomAction call %S failed with error 0x%x \n");
  }
}

```

## disassembly

```asm
0x180006830  push    rbx
0x180006832  push    rbp
0x180006833  push    rsi
0x180006834  push    rdi
0x180006835  push    r14
0x180006837  sub     rsp, 40h
0x18000683b  mov     r14d, edx
0x18000683e  mov     rcx, r8; String1
0x180006841  lea     rdx, aIisWorkerProce; "IIS_Worker_Process_Map_Config_Path"
0x180006848  mov     rbp, r9
0x18000684b  mov     rsi, r8
0x18000684e  call    wcscmp_0
0x180006853  test    eax, eax
0x180006855  jz      loc_18000696F
0x18000685b  mov     rdi, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x180006862  mov     ecx, 0A8h; Size
0x180006867  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000686c  mov     rbx, rax
0x18000686f  test    rax, rax
0x180006872  jz      loc_18000692B
0x180006878  mov     edx, 1; int
0x18000687d  mov     rcx, rax; this
0x180006880  call    ??0W3WP_HOST_WORKITEM@@QEAA@H@Z; W3WP_HOST_WORKITEM::W3WP_HOST_WORKITEM(int)
0x180006885  lea     rcx, ??_7RSCA_WORKITEM@@6B@; const RSCA_WORKITEM::`vftable'
0x18000688c  mov     qword ptr [rbx+28h], 0
0x180006894  mov     [rbx], rcx
0x180006897  lea     rcx, [rbx+38h]
0x18000689b  mov     dword ptr [rbx+30h], 0
0x1800068a2  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800068a8  lea     rcx, [rbx+70h]
0x1800068ac  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800068b2  mov     rax, [rdi]
0x1800068b5  mov     rcx, rdi
0x1800068b8  mov     rax, [rax]
0x1800068bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068c0  lea     rcx, [rbx+38h]
0x1800068c4  mov     [rbx+28h], rdi
0x1800068c8  mov     rdx, rsi
0x1800068cb  mov     [rbx+30h], r14d
0x1800068cf  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800068d5  mov     edi, eax
0x1800068d7  test    eax, eax
0x1800068d9  js      short loc_1800068FE
0x1800068db  lea     rcx, [rbx+70h]
0x1800068df  mov     rdx, rbp
0x1800068e2  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800068e8  mov     edi, eax
0x1800068ea  test    eax, eax
0x1800068ec  js      short loc_1800068FE
0x1800068ee  mov     rdx, rbx; struct W3WP_HOST_WORKITEM *
0x1800068f1  call    ?QueueWorkItem@W3WP_HOST@@QEAAJPEAVW3WP_HOST_WORKITEM@@@Z; W3WP_HOST::QueueWorkItem(W3WP_HOST_WORKITEM *)
0x1800068f6  mov     edi, eax
0x1800068f8  test    eax, eax
0x1800068fa  jns     short loc_18000696F
0x1800068fc  jmp     short loc_180006916
0x1800068fe  mov     rcx, [rbx+28h]
0x180006902  mov     rax, [rcx]
0x180006905  mov     rax, [rax+8]
0x180006909  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000690e  mov     qword ptr [rbx+28h], 0
0x180006916  mov     rax, [rbx]
0x180006919  mov     edx, 1
0x18000691e  mov     rcx, rbx
0x180006921  mov     rax, [rax]
0x180006924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006929  jmp     short loc_180006930
0x18000692b  mov     edi, 8007000Eh
0x180006930  test    byte ptr cs:g_dwDebugFlags, 3
0x180006937  jz      short loc_18000696F
0x180006939  mov     rcx, cs:g_pDebug
0x180006940  lea     rax, aCustomactionCa; "CustomAction call %S failed with error "...
0x180006947  mov     [rsp+68h+var_38], edi
0x18000694b  lea     r9, aW3wpHostReques; "W3WP_HOST::RequestCustomAction"
0x180006952  mov     [rsp+68h+var_40], rsi
0x180006957  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000695e  mov     r8d, 0F1Dh
0x180006964  mov     [rsp+68h+var_48], rax
0x180006969  call    cs:__imp_PuDbgPrint
0x18000696f  add     rsp, 40h
0x180006973  pop     r14
0x180006975  pop     rdi
0x180006976  pop     rsi
0x180006977  pop     rbp
0x180006978  pop     rbx
0x180006979  retn
```
