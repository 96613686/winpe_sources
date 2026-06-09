# WusaIsUUPHandler(IUpdate *)

- ea: `0x14000e5f4`
- end: `0x14000e784`
- name: `?WusaIsUUPHandler@@YA_NPEAUIUpdate@@@Z`
- size: `400`
- prototype: `bool __fastcall(struct IUpdate *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000e5f4`
- `0x14000f294`

## callees

- `0x14000e5f4`
- `0x140013490`
- `0x140015010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x14000e66d`
- `msvcrt!_wcsicmp` at `0x14000e66d`
- `OLEAUT32!__imp_SysFreeString` at `0x14000e774`
- `OLEAUT32!__imp_SysFreeString` at `0x14000e774`

## string_xrefs

- `0x14000e695`: `Failed to get update property BundledUpdates`
- `0x14000e620`: `update cannot be null`
- `0x14000e654`: `Failed to get update property HandlerID`
- `0x14000e666`: `http://schemas.microsoft.com/msus/2016/01/UpdateHandlers/OSInstaller`
- `0x14000e6bb`: `Failed to get update count`
- `0x14000e729`: `Failed to get update item`

## pseudocode

```c
char __fastcall WusaIsUUPHandler(struct IUpdate *a1)
{
  char v1; // bl
  unsigned int v3; // edi
  bool IsUUPHandler; // al
  struct IUpdate *v5; // rcx
  int v7; // [rsp+40h] [rbp+20h] BYREF
  struct IUpdate *v8; // [rsp+48h] [rbp+28h] BYREF
  __int64 v9; // [rsp+50h] [rbp+30h] BYREF
  wchar_t *String1; // [rsp+58h] [rbp+38h] BYREF

  v1 = 0;
  String1 = 0;
  v9 = 0;
  v7 = 0;
  if ( a1 )
  {
    if ( ((int (__fastcall *)(struct IUpdate *, wchar_t **))a1->lpVtbl->get_HandlerID)(a1, &String1) >= 0 )
    {
      if ( _wcsicmp(String1, L"http://schemas.microsoft.com/msus/2016/01/UpdateHandlers/OSInstaller") )
      {
        if ( ((int (__fastcall *)(struct IUpdate *, __int64 *))a1->lpVtbl->get_BundledUpdates)(a1, &v9) >= 0 )
        {
          if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v9 + 80LL))(v9, &v7) >= 0 )
          {
            if ( v7 > 0 )
            {
              v3 = 0;
              while ( 1 )
              {
                v8 = 0;
                if ( (*(int (__fastcall **)(__int64, _QWORD, struct IUpdate **))(*(_QWORD *)v9 + 56LL))(v9, v3, &v8) < 0 )
                  break;
                IsUUPHandler = WusaIsUUPHandler(v8);
                v5 = v8;
                if ( IsUUPHandler )
                {
                  v1 = 1;
                  goto LABEL_22;
                }
                if ( v8 )
                  ((void (*)(void))v8->lpVtbl->Release)();
                if ( (int)++v3 >= v7 )
                  goto LABEL_24;
              }
              WusaLogDebugEventA(L"WusaIsUUPHandler", 952, "Failed to get update item");
              v5 = v8;
LABEL_22:
              if ( v5 )
                ((void (__fastcall *)(struct IUpdate *))v5->lpVtbl->Release)(v5);
            }
          }
          else
          {
            WusaLogDebugEventA(L"WusaIsUUPHandler", 944, "Failed to get update count");
          }
        }
        else
        {
          WusaLogDebugEventA(L"WusaIsUUPHandler", 941, "Failed to get update property BundledUpdates");
        }
      }
      else
      {
        v1 = 1;
      }
    }
    else
    {
      WusaLogDebugEventA(L"WusaIsUUPHandler", 931, "Failed to get update property HandlerID");
    }
  }
  else
  {
    WusaLogDebugEventA(L"WusaIsUUPHandler", 928, "update cannot be null");
  }
LABEL_24:
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  if ( String1 )
    SysFreeString(String1);
  return v1;
}

```

## disassembly

```asm
0x14000e5f4  push    rbp
0x14000e5f6  push    rbx
0x14000e5f7  push    rdi
0x14000e5f8  mov     rbp, rsp
0x14000e5fb  sub     rsp, 20h
0x14000e5ff  xor     bl, bl
0x14000e601  mov     [rbp+String1], 0
0x14000e609  mov     [rbp+arg_10], 0
0x14000e611  mov     rdi, rcx
0x14000e614  mov     [rbp+arg_0], 0
0x14000e61b  test    rcx, rcx
0x14000e61e  jnz     short loc_14000E63D
0x14000e620  lea     r8, aUpdateCannotBe; "update cannot be null"
0x14000e627  mov     edx, 3A0h
0x14000e62c  lea     rcx, aWusaisuuphandl; "WusaIsUUPHandler"
0x14000e633  call    WusaLogDebugEventA
0x14000e638  jmp     loc_14000E756
0x14000e63d  mov     rax, [rcx]
0x14000e640  lea     rdx, [rbp+String1]
0x14000e644  mov     rax, [rax+90h]
0x14000e64b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e650  test    eax, eax
0x14000e652  jns     short loc_14000E662
0x14000e654  lea     r8, aFailedToGetUpd_2; "Failed to get update property HandlerID"
0x14000e65b  mov     edx, 3A3h
0x14000e660  jmp     short loc_14000E62C
0x14000e662  mov     rcx, [rbp+String1]; String1
0x14000e666  lea     rdx, aHttpSchemasMic; "http://schemas.microsoft.com/msus/2016/"...
0x14000e66d  call    cs:__imp__wcsicmp
0x14000e673  test    eax, eax
0x14000e675  jnz     short loc_14000E67E
0x14000e677  mov     bl, 1
0x14000e679  jmp     loc_14000E756
0x14000e67e  mov     rax, [rdi]
0x14000e681  lea     rdx, [rbp+arg_10]
0x14000e685  mov     rcx, rdi
0x14000e688  mov     rax, [rax+48h]
0x14000e68c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e691  test    eax, eax
0x14000e693  jns     short loc_14000E6A3
0x14000e695  lea     r8, aFailedToGetUpd_4; "Failed to get update property BundledUp"...
0x14000e69c  mov     edx, 3ADh
0x14000e6a1  jmp     short loc_14000E62C
0x14000e6a3  mov     rcx, [rbp+arg_10]
0x14000e6a7  lea     rdx, [rbp+arg_0]
0x14000e6ab  mov     rax, [rcx]
0x14000e6ae  mov     rax, [rax+50h]
0x14000e6b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e6b7  test    eax, eax
0x14000e6b9  jns     short loc_14000E6CC
0x14000e6bb  lea     r8, aFailedToGetUpd; "Failed to get update count"
0x14000e6c2  mov     edx, 3B0h
0x14000e6c7  jmp     loc_14000E62C
0x14000e6cc  cmp     [rbp+arg_0], 0
0x14000e6d0  jle     loc_14000E756
0x14000e6d6  xor     edi, edi
0x14000e6d8  mov     rcx, [rbp+arg_10]
0x14000e6dc  lea     r8, [rbp+arg_8]
0x14000e6e0  mov     [rbp+arg_8], 0
0x14000e6e8  mov     edx, edi
0x14000e6ea  mov     rax, [rcx]
0x14000e6ed  mov     rax, [rax+38h]
0x14000e6f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e6f6  test    eax, eax
0x14000e6f8  js      short loc_14000E729
0x14000e6fa  mov     rcx, [rbp+arg_8]; struct IUpdate *
0x14000e6fe  call    ?WusaIsUUPHandler@@YA_NPEAUIUpdate@@@Z; WusaIsUUPHandler(IUpdate *)
0x14000e703  mov     rcx, [rbp+arg_8]
0x14000e707  test    al, al
0x14000e709  jnz     short loc_14000E725
0x14000e70b  test    rcx, rcx
0x14000e70e  jz      short loc_14000E71C
0x14000e710  mov     rax, [rcx]
0x14000e713  mov     rax, [rax+10h]
0x14000e717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e71c  inc     edi
0x14000e71e  cmp     edi, [rbp+arg_0]
0x14000e721  jl      short loc_14000E6D8
0x14000e723  jmp     short loc_14000E756
0x14000e725  mov     bl, 1
0x14000e727  jmp     short loc_14000E745
0x14000e729  lea     r8, aFailedToGetUpd_6; "Failed to get update item"
0x14000e730  mov     edx, 3B8h
0x14000e735  lea     rcx, aWusaisuuphandl; "WusaIsUUPHandler"
0x14000e73c  call    WusaLogDebugEventA
0x14000e741  mov     rcx, [rbp+arg_8]
0x14000e745  test    rcx, rcx
0x14000e748  jz      short loc_14000E756
0x14000e74a  mov     rax, [rcx]
0x14000e74d  mov     rax, [rax+10h]
0x14000e751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e756  mov     rcx, [rbp+arg_10]
0x14000e75a  test    rcx, rcx
0x14000e75d  jz      short loc_14000E76B
0x14000e75f  mov     rax, [rcx]
0x14000e762  mov     rax, [rax+10h]
0x14000e766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e76b  mov     rcx, [rbp+String1]; bstrString
0x14000e76f  test    rcx, rcx
0x14000e772  jz      short loc_14000E77A
0x14000e774  call    cs:__imp_SysFreeString
0x14000e77a  mov     al, bl
0x14000e77c  add     rsp, 20h
0x14000e780  pop     rdi
0x14000e781  pop     rbx
0x14000e782  pop     rbp
0x14000e783  retn
```
