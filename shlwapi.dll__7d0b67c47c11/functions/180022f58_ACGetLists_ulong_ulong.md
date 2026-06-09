# ACGetLists(ulong,ulong)

- ea: `0x180022f58`
- end: `0x18002310c`
- name: `?ACGetLists@@YAPEAUIUnknown@@KK@Z`
- size: `436`
- prototype: `struct IUnknown *(unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180024830`

## callees

- `0x180012550`
- `0x180022f58`
- `0x1800237b8`
- `0x180023840`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180022fa1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023040`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800230a3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180022fa1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023040`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800230a3`

## string_xrefs

- `0x18002300a`: `Software\Microsoft\Windows\CurrentVersion\Explorer\TypedPaths`

## pseudocode

```c
struct IUnknown *__fastcall ACGetLists(char a1, unsigned int a2)
{
  struct IUnknown *v5; // [rsp+30h] [rbp-20h] BYREF
  struct IObjMgr *v6; // [rsp+38h] [rbp-18h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-10h] BYREF

  ppv = 0;
  if ( CoCreateInstance(&CLSID_ACLMulti, 0, 1u, &GUID_00000000_0000_0000_c000_000000000046, &ppv) >= 0 )
  {
    v6 = 0;
    if ( (**(int (__fastcall ***)(LPVOID, GUID *, struct IObjMgr **))ppv)(
           ppv,
           &GUID_00bb2761_6a77_11d0_a535_00c04fd7d062,
           &v6) >= 0 )
    {
      if ( (a1 & 4) != 0
        && (int)InitializeAndAddACLMRU(v6, L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\RunMRU") >= 0
        && (int)InitializeAndAddACLMRU(v6, L"Software\\Microsoft\\Internet Explorer\\TypedURLs") >= 0 )
      {
        InitializeAndAddACLMRU(v6, L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\TypedPaths");
      }
      if ( (a1 & 2) != 0 )
      {
        v5 = 0;
        if ( CoCreateInstance(&CLSID_ACLHistory, 0, 1u, &GUID_00000000_0000_0000_c000_000000000046, (LPVOID *)&v5) >= 0 )
        {
          ((void (__fastcall *)(struct IObjMgr *, struct IUnknown *))v6->lpVtbl[1].Remove)(v6, v5);
          IUnknown_SetOptions(v5, a2);
          ((void (__fastcall *)(struct IUnknown *))v5->lpVtbl->Release)(v5);
        }
      }
      if ( (a1 & 0x31) != 0 )
      {
        v5 = 0;
        if ( CoCreateInstance(&CLSID_ACListISF, 0, 1u, &GUID_00000000_0000_0000_c000_000000000046, (LPVOID *)&v5) >= 0 )
        {
          ((void (__fastcall *)(struct IObjMgr *, struct IUnknown *))v6->lpVtbl[1].Remove)(v6, v5);
          IUnknown_SetOptions(v5, a2);
          ((void (__fastcall *)(struct IUnknown *))v5->lpVtbl->Release)(v5);
        }
      }
      ((void (__fastcall *)(struct IObjMgr *))v6->lpVtbl[1].Append)(v6);
    }
  }
  return (struct IUnknown *)ppv;
}

```

## disassembly

```asm
0x180022f58  mov     [rsp-8+arg_0], rbx
0x180022f5d  mov     [rsp-8+arg_10], rdi
0x180022f62  push    rbp
0x180022f63  mov     rbp, rsp
0x180022f66  sub     rsp, 50h
0x180022f6a  mov     rax, cs:__security_cookie
0x180022f71  xor     rax, rsp
0x180022f74  mov     [rbp+var_8], rax
0x180022f78  mov     edi, edx
0x180022f7a  mov     [rbp+var_10], 0
0x180022f82  xor     edx, edx; pUnkOuter
0x180022f84  lea     rax, [rbp+var_10]
0x180022f88  mov     ebx, ecx
0x180022f8a  mov     [rsp+50h+ppv], rax; ppv
0x180022f8f  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180022f96  lea     rcx, CLSID_ACLMulti; rclsid
0x180022f9d  lea     r8d, [rdx+1]; dwClsContext
0x180022fa1  call    cs:__imp_CoCreateInstance
0x180022fa7  test    eax, eax
0x180022fa9  js      loc_1800230EC
0x180022faf  mov     rcx, [rbp+var_10]
0x180022fb3  lea     r8, [rbp+var_18]
0x180022fb7  mov     [rbp+var_18], 0
0x180022fbf  lea     rdx, _GUID_00bb2761_6a77_11d0_a535_00c04fd7d062
0x180022fc6  mov     rax, [rcx]
0x180022fc9  mov     rax, [rax]
0x180022fcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022fd1  test    eax, eax
0x180022fd3  js      loc_1800230EC
0x180022fd9  test    bl, 4
0x180022fdc  jz      short loc_180023016
0x180022fde  mov     rcx, [rbp+var_18]; struct IObjMgr *
0x180022fe2  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180022fe9  call    ?InitializeAndAddACLMRU@@YAJPEAUIObjMgr@@PEBG@Z; InitializeAndAddACLMRU(IObjMgr *,ushort const *)
0x180022fee  test    eax, eax
0x180022ff0  js      short loc_180023016
0x180022ff2  mov     rcx, [rbp+var_18]; struct IObjMgr *
0x180022ff6  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Internet Explorer"...
0x180022ffd  call    ?InitializeAndAddACLMRU@@YAJPEAUIObjMgr@@PEBG@Z; InitializeAndAddACLMRU(IObjMgr *,ushort const *)
0x180023002  test    eax, eax
0x180023004  js      short loc_180023016
0x180023006  mov     rcx, [rbp+var_18]; struct IObjMgr *
0x18002300a  lea     rdx, aSoftwareMicros_16; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180023011  call    ?InitializeAndAddACLMRU@@YAJPEAUIObjMgr@@PEBG@Z; InitializeAndAddACLMRU(IObjMgr *,ushort const *)
0x180023016  test    bl, 2
0x180023019  jz      short loc_180023079
0x18002301b  xor     edx, edx; pUnkOuter
0x18002301d  mov     [rbp+var_20], 0
0x180023025  lea     rax, [rbp+var_20]
0x180023029  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180023030  mov     [rsp+50h+ppv], rax; ppv
0x180023035  lea     rcx, CLSID_ACLHistory; rclsid
0x18002303c  lea     r8d, [rdx+1]; dwClsContext
0x180023040  call    cs:__imp_CoCreateInstance
0x180023046  test    eax, eax
0x180023048  js      short loc_180023079
0x18002304a  mov     rcx, [rbp+var_18]
0x18002304e  mov     rdx, [rbp+var_20]
0x180023052  mov     rax, [rcx]
0x180023055  mov     rax, [rax+18h]
0x180023059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002305e  mov     rcx, [rbp+var_20]; struct IUnknown *
0x180023062  mov     edx, edi; unsigned int
0x180023064  call    ?IUnknown_SetOptions@@YAJPEAUIUnknown@@K@Z; IUnknown_SetOptions(IUnknown *,ulong)
0x180023069  mov     rcx, [rbp+var_20]
0x18002306d  mov     rax, [rcx]
0x180023070  mov     rax, [rax+10h]
0x180023074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023079  test    bl, 31h
0x18002307c  jz      short loc_1800230DC
0x18002307e  xor     edx, edx; pUnkOuter
0x180023080  mov     [rbp+var_20], 0
0x180023088  lea     rax, [rbp+var_20]
0x18002308c  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180023093  mov     [rsp+50h+ppv], rax; ppv
0x180023098  lea     rcx, CLSID_ACListISF; rclsid
0x18002309f  lea     r8d, [rdx+1]; dwClsContext
0x1800230a3  call    cs:__imp_CoCreateInstance
0x1800230a9  test    eax, eax
0x1800230ab  js      short loc_1800230DC
0x1800230ad  mov     rcx, [rbp+var_18]
0x1800230b1  mov     rdx, [rbp+var_20]
0x1800230b5  mov     rax, [rcx]
0x1800230b8  mov     rax, [rax+18h]
0x1800230bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800230c1  mov     rcx, [rbp+var_20]; struct IUnknown *
0x1800230c5  mov     edx, edi; unsigned int
0x1800230c7  call    ?IUnknown_SetOptions@@YAJPEAUIUnknown@@K@Z; IUnknown_SetOptions(IUnknown *,ulong)
0x1800230cc  mov     rcx, [rbp+var_20]
0x1800230d0  mov     rax, [rcx]
0x1800230d3  mov     rax, [rax+10h]
0x1800230d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800230dc  mov     rcx, [rbp+var_18]
0x1800230e0  mov     rax, [rcx]
0x1800230e3  mov     rax, [rax+10h]
0x1800230e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800230ec  mov     rax, [rbp+var_10]
0x1800230f0  mov     rcx, [rbp+var_8]
0x1800230f4  xor     rcx, rsp; StackCookie
0x1800230f7  call    __security_check_cookie
0x1800230fc  mov     rbx, [rsp+50h+arg_0]
0x180023101  mov     rdi, [rsp+50h+arg_10]
0x180023106  add     rsp, 50h
0x18002310a  pop     rbp
0x18002310b  retn
```
