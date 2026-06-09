# CbsClient::CbsClient(ushort const *)

- ea: `0x140010aa0`
- end: `0x140010c22`
- name: `??0CbsClient@@QEAA@PEBG@Z`
- size: `386`
- prototype: `CbsClient *__fastcall(LPVOID *ppv, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000afc0`

## callees

- `0x14000e280`
- `0x140010aa0`
- `0x140013490`
- `0x140015010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140010c10`
- `KERNEL32!LocalFree` at `0x140010c10`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140010adf`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140010adf`

## string_xrefs

- `0x140010aee`: `Failed to create a CBS session instance`
- `0x140010b87`: `Failed to copy sand box location`

## pseudocode

```c
LPVOID *__fastcall CbsClient::CbsClient(LPVOID *ppv, const unsigned __int16 *a2)
{
  HRESULT Instance; // edi
  __int64 v5; // rax
  LPVOID *v6; // r8
  __int64 v7; // rdx
  LPVOID *v8; // rcx
  LPVOID v9; // rcx
  HLOCAL v10; // rsi
  HLOCAL hMem; // [rsp+60h] [rbp+8h] BYREF

  *ppv = 0;
  ppv[1] = 0;
  ppv[67] = 0;
  ppv[68] = 0;
  Instance = CoCreateInstance(
               &GUID_752073a1_23f2_4396_85f0_8fdb879ed0ed,
               0,
               0x15u,
               &GUID_75207391_23f2_4396_85f0_8fdb879ed0ed,
               ppv);
  if ( Instance < 0 )
  {
    WusaLogDebugEventA(L"CbsClient::CbsClient", 110, "Failed to create a CBS session instance");
    goto LABEL_13;
  }
  Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)*ppv + 24LL))(
               *ppv,
               0,
               L"wusa",
               0,
               0);
  if ( Instance < 0 )
  {
    WusaLogDebugEventA(L"CbsClient::CbsClient", 113, "Failed to initialize CBS session");
    goto LABEL_13;
  }
  v5 = 2147483646;
  v6 = ppv + 2;
  v7 = 260;
  do
  {
    if ( !v5 )
      break;
    if ( !*a2 )
      break;
    *(_WORD *)v6 = *a2++;
    v6 = (LPVOID *)((char *)v6 + 2);
    --v5;
    --v7;
  }
  while ( v7 );
  v8 = (LPVOID *)((char *)v6 - 2);
  Instance = v7 == 0 ? 0x8007007A : 0;
  if ( v7 )
    v8 = v6;
  *(_WORD *)v8 = 0;
  if ( !v7 )
  {
    WusaLogDebugEventA(L"CbsClient::CbsClient", 116, "Failed to copy sand box location");
LABEL_13:
    if ( Instance < 0 )
    {
      v9 = *ppv;
      if ( *ppv )
      {
        LODWORD(hMem) = 0;
        (*(void (__fastcall **)(LPVOID, HLOCAL *))(*(_QWORD *)v9 + 32LL))(v9, &hMem);
        if ( *ppv )
        {
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*ppv + 16LL))(*ppv);
          *ppv = 0;
        }
      }
      hMem = 0;
      WusaGetErrorMessage(Instance, (unsigned __int16 **)&hMem);
      v10 = hMem;
      WusaLogDebugEventA(
        L"CbsClient::CbsClient",
        127,
        "Exit with error code 0X%x (%ls)",
        Instance,
        (const wchar_t *)hMem);
      if ( v10 )
        LocalFree(v10);
    }
  }
  return ppv;
}

```

## disassembly

```asm
0x140010aa0  push    rbx
0x140010aa2  push    rbp
0x140010aa3  push    rsi
0x140010aa4  push    rdi
0x140010aa5  sub     rsp, 38h
0x140010aa9  xor     ebp, ebp
0x140010aab  mov     [rsp+58h+ppv], rcx; ppv
0x140010ab0  mov     rsi, rdx
0x140010ab3  mov     [rcx], rbp
0x140010ab6  mov     rbx, rcx
0x140010ab9  mov     [rcx+8], rbp
0x140010abd  mov     [rcx+218h], rbp
0x140010ac4  lea     r9, _GUID_75207391_23f2_4396_85f0_8fdb879ed0ed; riid
0x140010acb  mov     [rcx+220h], rbp
0x140010ad2  lea     r8d, [rbp+15h]; dwClsContext
0x140010ad6  xor     edx, edx; pUnkOuter
0x140010ad8  lea     rcx, _GUID_752073a1_23f2_4396_85f0_8fdb879ed0ed; rclsid
0x140010adf  call    cs:__imp_CoCreateInstance
0x140010ae5  mov     edi, eax
0x140010ae7  test    eax, eax
0x140010ae9  jns     short loc_140010AFA
0x140010aeb  lea     edx, [rbp+6Eh]
0x140010aee  lea     r8, aFailedToCreate_9; "Failed to create a CBS session instance"
0x140010af5  jmp     loc_140010B8E
0x140010afa  mov     rcx, [rbx]
0x140010afd  lea     r8, aWusa_1; "wusa"
0x140010b04  xor     r9d, r9d
0x140010b07  mov     [rsp+58h+ppv], rbp
0x140010b0c  xor     edx, edx
0x140010b0e  mov     rax, [rcx]
0x140010b11  mov     rax, [rax+18h]
0x140010b15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010b1a  mov     edi, eax
0x140010b1c  test    eax, eax
0x140010b1e  jns     short loc_140010B2E
0x140010b20  mov     edx, 71h ; 'q'
0x140010b25  lea     r8, aFailedToInitia; "Failed to initialize CBS session"
0x140010b2c  jmp     short loc_140010B8E
0x140010b2e  mov     eax, 7FFFFFFEh
0x140010b33  lea     r8, [rbx+10h]
0x140010b37  mov     edx, 104h
0x140010b3c  test    rax, rax
0x140010b3f  jz      short loc_140010B5E
0x140010b41  movzx   ecx, word ptr [rsi]
0x140010b44  test    cx, cx
0x140010b47  jz      short loc_140010B5E
0x140010b49  mov     [r8], cx
0x140010b4d  add     rsi, 2
0x140010b51  add     r8, 2
0x140010b55  dec     rax
0x140010b58  sub     rdx, 1
0x140010b5c  jnz     short loc_140010B3C
0x140010b5e  mov     rax, rdx
0x140010b61  lea     rcx, [r8-2]
0x140010b65  neg     rax
0x140010b68  sbb     edi, edi
0x140010b6a  not     edi
0x140010b6c  and     edi, 8007007Ah
0x140010b72  test    rdx, rdx
0x140010b75  cmovnz  rcx, r8
0x140010b79  mov     [rcx], bp
0x140010b7c  jnz     loc_140010C16
0x140010b82  mov     edx, 74h ; 't'
0x140010b87  lea     r8, aFailedToCopySa; "Failed to copy sand box location"
0x140010b8e  lea     rcx, aCbsclientCbscl; "CbsClient::CbsClient"
0x140010b95  call    WusaLogDebugEventA
0x140010b9a  test    edi, edi
0x140010b9c  jns     short loc_140010C16
0x140010b9e  mov     rcx, [rbx]
0x140010ba1  test    rcx, rcx
0x140010ba4  jz      short loc_140010BD2
0x140010ba6  mov     dword ptr [rsp+58h+hMem], ebp
0x140010baa  lea     rdx, [rsp+58h+hMem]
0x140010baf  mov     rax, [rcx]
0x140010bb2  mov     rax, [rax+20h]
0x140010bb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010bbb  mov     rcx, [rbx]
0x140010bbe  test    rcx, rcx
0x140010bc1  jz      short loc_140010BD2
0x140010bc3  mov     rax, [rcx]
0x140010bc6  mov     rax, [rax+10h]
0x140010bca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010bcf  mov     [rbx], rbp
0x140010bd2  lea     rdx, [rsp+58h+hMem]; unsigned __int16 **
0x140010bd7  mov     [rsp+58h+hMem], rbp
0x140010bdc  mov     ecx, edi; dwMessageId
0x140010bde  call    ?WusaGetErrorMessage@@YAJKPEAPEAG@Z; WusaGetErrorMessage(ulong,ushort * *)
0x140010be3  mov     rsi, [rsp+58h+hMem]
0x140010be8  lea     r8, aExitWithErrorC; "Exit with error code 0X%x (%ls)"
0x140010bef  mov     r9d, edi
0x140010bf2  mov     [rsp+58h+ppv], rsi
0x140010bf7  mov     edx, 7Fh
0x140010bfc  lea     rcx, aCbsclientCbscl; "CbsClient::CbsClient"
0x140010c03  call    WusaLogDebugEventA
0x140010c08  test    rsi, rsi
0x140010c0b  jz      short loc_140010C16
0x140010c0d  mov     rcx, rsi; hMem
0x140010c10  call    cs:__imp_LocalFree
0x140010c16  mov     rax, rbx
0x140010c19  add     rsp, 38h
0x140010c1d  pop     rdi
0x140010c1e  pop     rsi
0x140010c1f  pop     rbp
0x140010c20  pop     rbx
0x140010c21  retn
```
