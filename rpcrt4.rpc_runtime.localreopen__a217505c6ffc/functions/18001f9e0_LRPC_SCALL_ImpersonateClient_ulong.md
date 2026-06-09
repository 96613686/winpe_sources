# LRPC_SCALL::ImpersonateClient(ulong)

- ea: `0x18001f9e0`
- end: `0x18001fc3d`
- name: `?ImpersonateClient@LRPC_SCALL@@UEAAJK@Z`
- size: `605`
- prototype: `__int64 __fastcall(LRPC_SCALL *this, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18007e840`
- `0x1800abac0`

## callees

- `0x18001e7d0`
- `0x18001f9e0`
- `0x1800293c4`
- `0x1800295d8`
- `0x18008c2e8`
- `0x1800a890c`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x18001fb79`
- `ntdll!NtSetInformationThread` at `0x18001fb79`
- `ntdll!NtAlpcImpersonateClientOfPort` at `0x18001fa3e`
- `ntdll!NtAlpcImpersonateClientOfPort` at `0x18001fa95`
- `ntdll!NtAlpcImpersonateClientOfPort` at `0x18001fa3e`
- `ntdll!NtAlpcImpersonateClientOfPort` at `0x18001fa95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001fb58`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001fb58`

## pseudocode

```c
__int64 __fastcall LRPC_SCALL::ImpersonateClient(LRPC_SCALL *this, int a2)
{
  struct THREAD *v4; // rax
  int v5; // ebx
  int v6; // eax
  unsigned int v7; // ebx
  struct THREAD *v8; // rax
  bool v10; // zf
  bool v11; // zf
  __int64 v12; // rsi
  HANDLE CurrentThread; // rax
  int v14; // ebx
  _DWORD v15[10]; // [rsp+30h] [rbp-28h] BYREF

  v4 = ThreadSelf();
  if ( v4 )
  {
    *((_QWORD *)v4 + 5) = -1;
    if ( !*((_QWORD *)this + 74) )
    {
      v5 = a2 - 1;
      if ( v5 )
      {
        if ( v5 != 1 )
        {
          v7 = 1764;
          goto LABEL_8;
        }
        v6 = NtAlpcImpersonateClientOfPort(*(_QWORD *)(*((_QWORD *)this + 38) + 48LL), *((_QWORD *)this + 55), 1);
        if ( !v6 )
          goto LABEL_6;
        v10 = v6 == -1073741670;
        if ( v6 > -1073741670 )
        {
          if ( v6 == -1073741281 || v6 == -1073740030 )
            goto LABEL_23;
          v11 = v6 == -1073740029;
LABEL_22:
          if ( v11 )
          {
LABEL_23:
            v7 = 1765;
            goto LABEL_24;
          }
LABEL_15:
          v7 = 5;
LABEL_24:
          v15[2] = v6;
          v15[0] = 3;
          RpcpErrorAddRecord(2u, v7, 0x4BAu, 1, (struct tagParam *)v15);
          goto LABEL_7;
        }
      }
      else
      {
        v6 = NtAlpcImpersonateClientOfPort(*(_QWORD *)(*((_QWORD *)this + 38) + 48LL), *((_QWORD *)this + 55), 0);
        if ( !v6 )
        {
LABEL_6:
          v7 = 0;
          goto LABEL_7;
        }
        v10 = v6 == -1073741670;
        if ( v6 > -1073741670 )
        {
          if ( v6 != -1073741659 && (v6 == -1073741281 || v6 == -1073740030 || v6 == -1073740029) )
            goto LABEL_23;
          goto LABEL_15;
        }
      }
      if ( v10 )
      {
        v7 = 1721;
        goto LABEL_24;
      }
      switch ( v6 )
      {
        case -1073741813:
          goto LABEL_23;
        case -1073741801:
          v7 = 14;
          goto LABEL_24;
        case -1073741790:
          goto LABEL_23;
      }
      v11 = v6 == -1073741769;
      goto LABEL_22;
    }
    if ( (*((_DWORD *)this + 58) & 0x40) != 0 )
    {
      v7 = LRPC_SCALL::ImpersonateFromCallbackData(this);
    }
    else
    {
      v12 = *(_QWORD *)(*((_QWORD *)this + 74) + 24LL);
      if ( *(_DWORD *)(v12 + 148) )
      {
        CurrentThread = GetCurrentThread();
        NtSetInformationThread(CurrentThread, ThreadImpersonationToken, (PVOID)(v12 + 160), 8u);
        return 0;
      }
      v14 = a2 - 1;
      if ( v14 )
      {
        if ( v14 != 1 )
        {
          v7 = 1764;
          goto LABEL_8;
        }
        v7 = LRPC_SASSOCIATION::ImpersonateClientEx(
               *((LRPC_SASSOCIATION **)this + 38),
               *((struct _PORT_MESSAGE **)this + 55));
      }
      else
      {
        v7 = LRPC_SASSOCIATION::ImpersonateClient(
               *((LRPC_SASSOCIATION **)this + 38),
               *((struct _PORT_MESSAGE **)this + 55));
      }
    }
LABEL_7:
    if ( !v7 )
      return v7;
LABEL_8:
    v8 = ThreadSelf();
    if ( v8 )
    {
      if ( *((_QWORD *)v8 + 5) )
        *((_QWORD *)v8 + 5) = 0;
    }
    return v7;
  }
  return 14;
}

```

## disassembly

```asm
0x18001f9e0  mov     [rsp+arg_8], rbx
0x18001f9e5  push    rdi
0x18001f9e6  sub     rsp, 50h
0x18001f9ea  mov     ebx, edx
0x18001f9ec  mov     rdi, rcx
0x18001f9ef  call    ?ThreadSelf@@YAPEAVTHREAD@@XZ; ThreadSelf(void)
0x18001f9f4  test    rax, rax
0x18001f9f7  jz      loc_18001FC33
0x18001f9fd  mov     qword ptr [rax+28h], 0FFFFFFFFFFFFFFFFh
0x18001fa05  cmp     qword ptr [rdi+250h], 0
0x18001fa0d  mov     [rsp+58h+arg_0], rsi
0x18001fa12  jnz     loc_18001FB38
0x18001fa18  sub     ebx, 1
0x18001fa1b  jz      short loc_18001FA80
0x18001fa1d  cmp     ebx, 1
0x18001fa20  jnz     loc_18001FBC6
0x18001fa26  mov     rcx, [rdi+130h]
0x18001fa2d  mov     r8d, 1
0x18001fa33  mov     rdx, [rdi+1B8h]
0x18001fa3a  mov     rcx, [rcx+30h]
0x18001fa3e  call    cs:__imp_NtAlpcImpersonateClientOfPort
0x18001fa45  nop     dword ptr [rax+rax+00h]
0x18001fa4a  test    eax, eax
0x18001fa4c  jnz     short loc_18001FABE
0x18001fa4e  xor     ebx, ebx
0x18001fa50  test    ebx, ebx
0x18001fa52  jz      short loc_18001FA6D
0x18001fa54  call    ?ThreadSelf@@YAPEAVTHREAD@@XZ; ThreadSelf(void)
0x18001fa59  test    rax, rax
0x18001fa5c  jz      short loc_18001FA6D
0x18001fa5e  cmp     qword ptr [rax+28h], 0
0x18001fa63  jz      short loc_18001FA6D
0x18001fa65  mov     qword ptr [rax+28h], 0
0x18001fa6d  mov     rsi, [rsp+58h+arg_0]
0x18001fa72  mov     eax, ebx
0x18001fa74  mov     rbx, [rsp+58h+arg_8]
0x18001fa79  add     rsp, 50h
0x18001fa7d  pop     rdi
0x18001fa7e  retn
0x18001fa80  mov     rcx, [rdi+130h]
0x18001fa87  xor     r8d, r8d
0x18001fa8a  mov     rdx, [rdi+1B8h]
0x18001fa91  mov     rcx, [rcx+30h]
0x18001fa95  call    cs:__imp_NtAlpcImpersonateClientOfPort
0x18001fa9c  nop     dword ptr [rax+rax+00h]
0x18001faa1  test    eax, eax
0x18001faa3  jz      short loc_18001FA4E
0x18001faa5  cmp     eax, 0C000009Ah
0x18001faaa  jle     short loc_18001FAC5
0x18001faac  cmp     eax, 0C00000A5h
0x18001fab1  jnz     loc_18001FC0D
0x18001fab7  mov     ebx, 5
0x18001fabc  jmp     short loc_18001FAF0
0x18001fabe  cmp     eax, 0C000009Ah
0x18001fac3  jg      short loc_18001FB23
0x18001fac5  jz      loc_18001FC03
0x18001facb  cmp     eax, 0C000000Bh
0x18001fad0  jz      short loc_18001FAEB
0x18001fad2  cmp     eax, 0C0000017h
0x18001fad7  jz      loc_18001FBF9
0x18001fadd  cmp     eax, 0C0000022h
0x18001fae2  jz      short loc_18001FAEB
0x18001fae4  cmp     eax, 0C0000037h
0x18001fae9  jnz     short loc_18001FAB7
0x18001faeb  mov     ebx, 6E5h
0x18001faf0  mov     [rsp+58h+var_20], eax
0x18001faf4  mov     r9d, 1; int
0x18001fafa  lea     rax, [rsp+58h+var_28]
0x18001faff  mov     [rsp+58h+var_28], 3
0x18001fb07  mov     r8d, 4BAh; unsigned __int16
0x18001fb0d  mov     [rsp+58h+var_38], rax; struct tagParam *
0x18001fb12  mov     edx, ebx; int
0x18001fb14  mov     ecx, 2; unsigned int
0x18001fb19  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x18001fb1e  jmp     loc_18001FA50
0x18001fb23  cmp     eax, 0C000021Fh
0x18001fb28  jz      short loc_18001FAEB
0x18001fb2a  cmp     eax, 0C0000702h
0x18001fb2f  jz      short loc_18001FAEB
0x18001fb31  cmp     eax, 0C0000703h
0x18001fb36  jmp     short loc_18001FAE9
0x18001fb38  mov     eax, [rdi+0E8h]
0x18001fb3e  test    al, 40h
0x18001fb40  jnz     short loc_18001FB98
0x18001fb42  mov     rax, [rdi+250h]
0x18001fb49  mov     rsi, [rax+18h]
0x18001fb4d  cmp     dword ptr [rsi+94h], 0
0x18001fb54  jz      short loc_18001FBA7
0x18001fb56  xor     ebx, ebx
0x18001fb58  call    cs:__imp_GetCurrentThread
0x18001fb5f  nop     dword ptr [rax+rax+00h]
0x18001fb64  lea     r8, [rsi+0A0h]; ThreadInformation
0x18001fb6b  mov     edx, 5; ThreadInformationClass
0x18001fb70  mov     rcx, rax; ThreadHandle
0x18001fb73  mov     r9d, 8; ThreadInformationLength
0x18001fb79  call    cs:__imp_NtSetInformationThread
0x18001fb80  nop     dword ptr [rax+rax+00h]
0x18001fb85  mov     rsi, [rsp+58h+arg_0]
0x18001fb8a  mov     eax, ebx
0x18001fb8c  mov     rbx, [rsp+58h+arg_8]
0x18001fb91  add     rsp, 50h
0x18001fb95  pop     rdi
0x18001fb96  retn
0x18001fb98  mov     rcx, rdi; this
0x18001fb9b  call    ?ImpersonateFromCallbackData@LRPC_SCALL@@AEAAJXZ; LRPC_SCALL::ImpersonateFromCallbackData(void)
0x18001fba0  mov     ebx, eax
0x18001fba2  jmp     loc_18001FA50
0x18001fba7  sub     ebx, 1
0x18001fbaa  jnz     short loc_18001FBD0
0x18001fbac  mov     rdx, [rdi+1B8h]; struct _PORT_MESSAGE *
0x18001fbb3  mov     rcx, [rdi+130h]; this
0x18001fbba  call    ?ImpersonateClient@LRPC_SASSOCIATION@@QEAAJPEAU_PORT_MESSAGE@@@Z; LRPC_SASSOCIATION::ImpersonateClient(_PORT_MESSAGE *)
0x18001fbbf  mov     ebx, eax
0x18001fbc1  jmp     loc_18001FA50
0x18001fbc6  mov     ebx, 6E4h
0x18001fbcb  jmp     loc_18001FA54
0x18001fbd0  cmp     ebx, 1
0x18001fbd3  jz      short loc_18001FBDF
0x18001fbd5  mov     ebx, 6E4h
0x18001fbda  jmp     loc_18001FA54
0x18001fbdf  mov     rdx, [rdi+1B8h]; struct _PORT_MESSAGE *
0x18001fbe6  mov     rcx, [rdi+130h]; this
0x18001fbed  call    ?ImpersonateClientEx@LRPC_SASSOCIATION@@QEAAJPEAU_PORT_MESSAGE@@@Z; LRPC_SASSOCIATION::ImpersonateClientEx(_PORT_MESSAGE *)
0x18001fbf2  mov     ebx, eax
0x18001fbf4  jmp     loc_18001FA50
0x18001fbf9  mov     ebx, 0Eh
0x18001fbfe  jmp     loc_18001FAF0
0x18001fc03  mov     ebx, 6B9h
0x18001fc08  jmp     loc_18001FAF0
0x18001fc0d  cmp     eax, 0C000021Fh
0x18001fc12  jz      loc_18001FAEB
0x18001fc18  cmp     eax, 0C0000702h
0x18001fc1d  jz      loc_18001FAEB
0x18001fc23  cmp     eax, 0C0000703h
0x18001fc28  jnz     loc_18001FAB7
0x18001fc2e  jmp     loc_18001FAEB
0x18001fc33  mov     eax, 0Eh
0x18001fc38  jmp     loc_18001FA74
```
