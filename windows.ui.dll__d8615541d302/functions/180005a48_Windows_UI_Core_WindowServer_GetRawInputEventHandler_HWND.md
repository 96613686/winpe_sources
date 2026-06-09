# Windows::UI::Core::WindowServer::GetRawInputEventHandler(HWND__ *)

- ea: `0x180005a48`
- end: `0x180005bb6`
- name: `?GetRawInputEventHandler@WindowServer@Core@UI@Windows@@AEAA?AV?$ComPtr@UIRawInputEventHandler@@@WRL@Microsoft@@PEAUHWND__@@@Z`
- size: `366`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180005c60`
- `0x180005e00`

## callees

- `0x1800038e0`
- `0x180005a48`
- `0x1800ca010`

## import_xrefs

- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180005b0e`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180005b0e`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x180005aa6`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x180005b57`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x180005aa6`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x180005b57`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Windows::UI::Core::WindowServer::GetRawInputEventHandler(__int64 a1, _QWORD *a2, __int64 a3)
{
  int WindowService; // eax
  __int64 v7; // rcx
  __int64 v9; // rcx
  _QWORD v10[2]; // [rsp+20h] [rbp-10h] BYREF
  int v11; // [rsp+68h] [rbp+38h] BYREF

  if ( !byte_18013544A )
  {
    v11 = 0;
    RtlGetDeviceFamilyInfoEnum(0, &v11, 0);
    if ( v11 == 5 || (unsigned int)(v11 - 11) <= 1 )
    {
      byte_180135448 = 1;
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(a1 + 3360);
      byte_180135449 = (int)CoreQueryWindowService(
                              a3,
                              &GUID_94b9c18a_727b_419e_ba04_9cc0ffe8642f,
                              &GUID_94b9c18a_727b_419e_ba04_9cc0ffe8642f,
                              a1 + 3360) >= 0;
    }
    else
    {
      byte_180135448 = 0;
    }
    byte_18013544A = 1;
  }
  if ( byte_180135448 )
  {
    if ( byte_180135449 )
    {
      v9 = *(_QWORD *)(a1 + 3360);
      *a2 = v9;
      if ( v9 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
    }
    else
    {
      *a2 = 0;
    }
  }
  else
  {
    v10[0] = 0;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(v10);
    WindowService = CoreQueryWindowService(
                      a3,
                      &GUID_94b9c18a_727b_419e_ba04_9cc0ffe8642f,
                      &GUID_94b9c18a_727b_419e_ba04_9cc0ffe8642f,
                      v10);
    *a2 = 0;
    if ( WindowService >= 0 )
    {
      if ( a2 == v10 )
      {
        v7 = v10[0];
      }
      else
      {
        *a2 = v10[0];
        v7 = 0;
      }
    }
    else
    {
      v7 = v10[0];
    }
    if ( v7 )
    {
      v10[0] = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x180005a48  mov     [rsp-18h+arg_0], rbx
0x180005a4d  mov     [rsp-18h+arg_8], rsi
0x180005a52  push    rbp
0x180005a53  push    rdi
0x180005a54  push    r14
0x180005a56  mov     rbp, rsp
0x180005a59  sub     rsp, 30h
0x180005a5d  mov     r14, r8
0x180005a60  mov     rdi, rdx
0x180005a63  mov     rsi, rcx
0x180005a66  cmp     cs:byte_18013544A, 0
0x180005a6d  jz      loc_180005AFE
0x180005a73  cmp     cs:byte_180135448, 0
0x180005a7a  jnz     loc_180005B74
0x180005a80  mov     [rbp+var_10], 0
0x180005a88  lea     rcx, [rbp+var_10]
0x180005a8c  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180005a91  lea     r9, [rbp+var_10]
0x180005a95  lea     r8, _GUID_94b9c18a_727b_419e_ba04_9cc0ffe8642f
0x180005a9c  lea     rdx, _GUID_94b9c18a_727b_419e_ba04_9cc0ffe8642f
0x180005aa3  mov     rcx, r14
0x180005aa6  call    cs:__imp_CoreQueryWindowService
0x180005aac  mov     qword ptr [rdi], 0
0x180005ab3  test    eax, eax
0x180005ab5  jns     short loc_180005AEB
0x180005ab7  mov     rcx, [rbp+var_10]
0x180005abb  test    rcx, rcx
0x180005abe  jz      short loc_180005AD5
0x180005ac0  mov     [rbp+var_10], 0
0x180005ac8  mov     rax, [rcx]
0x180005acb  mov     rax, [rax+10h]
0x180005acf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ad4  nop
0x180005ad5  mov     rax, rdi
0x180005ad8  mov     rbx, [rsp+30h+arg_0]
0x180005add  mov     rsi, [rsp+30h+arg_8]
0x180005ae2  add     rsp, 30h
0x180005ae6  pop     r14
0x180005ae8  pop     rdi
0x180005ae9  pop     rbp
0x180005aea  retn
0x180005aeb  lea     rax, [rbp+var_10]
0x180005aef  cmp     rdi, rax
0x180005af2  jnz     loc_180005BA8
0x180005af8  mov     rcx, [rbp+var_10]
0x180005afc  jmp     short loc_180005ABB
0x180005afe  mov     [rbp+arg_18], 0
0x180005b05  xor     r8d, r8d
0x180005b08  lea     rdx, [rbp+arg_18]
0x180005b0c  xor     ecx, ecx
0x180005b0e  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x180005b14  mov     eax, [rbp+arg_18]
0x180005b17  cmp     eax, 5
0x180005b1a  jz      short loc_180005B2D
0x180005b1c  add     eax, 0FFFFFFF5h
0x180005b1f  cmp     eax, 1
0x180005b22  jbe     short loc_180005B2D
0x180005b24  mov     cs:byte_180135448, 0
0x180005b2b  jmp     short loc_180005B68
0x180005b2d  mov     cs:byte_180135448, 1
0x180005b34  lea     rbx, [rsi+0D20h]
0x180005b3b  mov     rcx, rbx
0x180005b3e  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180005b43  mov     r9, rbx
0x180005b46  lea     r8, _GUID_94b9c18a_727b_419e_ba04_9cc0ffe8642f
0x180005b4d  lea     rdx, _GUID_94b9c18a_727b_419e_ba04_9cc0ffe8642f
0x180005b54  mov     rcx, r14
0x180005b57  call    cs:__imp_CoreQueryWindowService
0x180005b5d  shr     eax, 1Fh
0x180005b60  xor     al, 1
0x180005b62  mov     cs:byte_180135449, al
0x180005b68  mov     cs:byte_18013544A, 1
0x180005b6f  jmp     loc_180005A73
0x180005b74  cmp     cs:byte_180135449, 0
0x180005b7b  jz      short loc_180005B9C
0x180005b7d  mov     rcx, [rsi+0D20h]
0x180005b84  mov     [rdi], rcx
0x180005b87  test    rcx, rcx
0x180005b8a  jz      loc_180005AD5
0x180005b90  mov     rax, [rcx]
0x180005b93  mov     rax, [rax+8]
0x180005b97  jmp     loc_180005ACF
0x180005b9c  mov     qword ptr [rdi], 0
0x180005ba3  jmp     loc_180005AD5
0x180005ba8  mov     rax, [rbp+var_10]
0x180005bac  mov     [rdi], rax
0x180005baf  xor     ecx, ecx
0x180005bb1  jmp     loc_180005AFC
```
