# TpmEvtDeviceFileCreate

- ea: `0x140013bf0`
- end: `0x140013d55`
- name: `TpmEvtDeviceFileCreate`
- size: `357`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation`

## callees

- `0x140004520`
- `0x140007a94`
- `0x140008da0`
- `0x140013bf0`
- `0x140013d5c`
- `0x1400155f8`
- `0x140039740`
- `0x140039780`

## pseudocode

```c
__int64 __fastcall TpmEvtDeviceFileCreate(__int64 a1, __int64 a2, __int64 a3)
{
  BOOL v6; // esi
  struct _FILE_OBJECT *v7; // rdi
  int v8; // eax
  __int64 v9; // r8
  unsigned int v10; // eax
  TpmDevice **v11; // rax
  struct TpmStack *v12; // rbx
  int Context; // eax
  struct Tpm20Context *v15; // [rsp+20h] [rbp-40h] BYREF
  __int128 v16; // [rsp+28h] [rbp-38h] BYREF
  __int128 v17; // [rsp+38h] [rbp-28h]
  __int64 v18; // [rsp+48h] [rbp-18h]

  v18 = 0;
  v16 = 0;
  LOWORD(v16) = 40;
  v17 = 0;
  (*((void (__fastcall **)(PKDPC, __int64, __int128 *))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 266))(
    WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
    a2,
    &v16);
  v6 = WORD5(v17) == 0;
  v7 = (struct _FILE_OBJECT *)(*((__int64 (__fastcall **)(PKDPC, __int64))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 140))(
                                WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
                                a3);
  v8 = TpmCheckDriverState(v7);
  v9 = (unsigned int)v8;
  if ( v8 >= 0 )
  {
    if ( !v6 || (v10 = TpmAccessCheck(2), (v9 = v10) == 0) )
    {
      v15 = 0;
      v11 = (TpmDevice **)(*((__int64 (__fastcall **)(PKDPC, __int64, void *))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 202))(
                            WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
                            a1,
                            off_140047018);
      v12 = (struct TpmStack *)v11;
      if ( TpmTransportType::m_Version == 1 )
      {
        Context = TpmDevice::CreateContext(*v11, (void **)&v15);
      }
      else
      {
        v15 = 0;
        Context = Tpm20ResourceMgr::CreateTpm20Context(&v15);
      }
      v9 = (unsigned int)Context;
      if ( Context >= 0 )
      {
        v7->FsContext = v15;
        if ( v6 )
          WPP_MAIN_CB.Queue.ListEntry.Blink = (struct _LIST_ENTRY *)v7;
        v9 = (unsigned int)TpmSetDriverState(v12);
      }
    }
  }
  return (*((__int64 (__fastcall **)(PKDPC, __int64, __int64))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 263))(
           WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
           a2,
           v9);
}

```

## disassembly

```asm
0x140013bf0  push    rbp
0x140013bf2  push    rbx
0x140013bf3  push    rsi
0x140013bf4  push    rdi
0x140013bf5  push    r12
0x140013bf7  push    r14
0x140013bf9  push    r15
0x140013bfb  mov     rbp, rsp
0x140013bfe  sub     rsp, 60h
0x140013c02  mov     rax, cs:__security_cookie
0x140013c09  xor     rax, rsp
0x140013c0c  mov     [rbp+var_10], rax
0x140013c10  xor     eax, eax
0x140013c12  xorps   xmm0, xmm0
0x140013c15  mov     [rbp+var_18], rax
0x140013c19  mov     rbx, r8
0x140013c1c  movups  [rbp+var_38], xmm0
0x140013c20  mov     eax, 28h ; '('
0x140013c25  lea     r8, [rbp+var_38]
0x140013c29  mov     word ptr [rbp+var_38], ax
0x140013c2d  mov     r15, rcx
0x140013c30  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x140013c37  mov     r14, rdx
0x140013c3a  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x140013c41  movups  [rbp+var_28], xmm0
0x140013c45  mov     rax, [rax+850h]
0x140013c4c  call    _guard_dispatch_icall
0x140013c51  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x140013c58  xor     r12d, r12d
0x140013c5b  cmp     word ptr [rbp+var_28+0Ah], r12w
0x140013c60  mov     esi, r12d
0x140013c63  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x140013c6a  mov     rdx, rbx
0x140013c6d  setz    sil
0x140013c71  mov     rax, [rax+460h]
0x140013c78  call    _guard_dispatch_icall
0x140013c7d  mov     rcx, rax; struct _FILE_OBJECT *
0x140013c80  mov     rdi, rax
0x140013c83  call    ?TpmCheckDriverState@@YAJPEAU_FILE_OBJECT@@@Z; TpmCheckDriverState(_FILE_OBJECT *)
0x140013c88  mov     r8d, eax
0x140013c8b  test    eax, eax
0x140013c8d  js      loc_140013D1C
0x140013c93  test    esi, esi
0x140013c95  jz      short loc_140013CA8
0x140013c97  lea     ecx, [r12+2]
0x140013c9c  call    ?TpmAccessCheck@@YAJW4_USER_TYPE@@@Z; TpmAccessCheck(_USER_TYPE)
0x140013ca1  mov     r8d, eax
0x140013ca4  test    eax, eax
0x140013ca6  jnz     short loc_140013D1C
0x140013ca8  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x140013caf  mov     rdx, r15
0x140013cb2  mov     r8, cs:off_140047018
0x140013cb9  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x140013cc0  mov     [rbp+var_40], r12
0x140013cc4  mov     rax, [rax+650h]
0x140013ccb  call    _guard_dispatch_icall
0x140013cd0  cmp     cs:?m_Version@TpmTransportType@@0W4VERSION@1@A, 1; TpmTransportType::VERSION TpmTransportType::m_Version
0x140013cd7  mov     rbx, rax
0x140013cda  jnz     short loc_140013CEA
0x140013cdc  mov     rcx, [rax]; this
0x140013cdf  lea     rdx, [rbp+var_40]; void **
0x140013ce3  call    ?CreateContext@TpmDevice@@QEAAJPEAPEAX@Z; TpmDevice::CreateContext(void * *)
0x140013ce8  jmp     short loc_140013CF7
0x140013cea  lea     rcx, [rbp+var_40]; struct Tpm20Context **
0x140013cee  mov     [rbp+var_40], r12
0x140013cf2  call    ?CreateTpm20Context@Tpm20ResourceMgr@@SAJPEAPEAVTpm20Context@@@Z; Tpm20ResourceMgr::CreateTpm20Context(Tpm20Context * *)
0x140013cf7  mov     r8d, eax
0x140013cfa  test    eax, eax
0x140013cfc  js      short loc_140013D1C
0x140013cfe  mov     rcx, [rbp+var_40]
0x140013d02  mov     [rdi+18h], rcx
0x140013d06  test    esi, esi
0x140013d08  jz      short loc_140013D11
0x140013d0a  mov     qword ptr cs:WPP_MAIN_CB.Queue+8, rdi
0x140013d11  mov     rcx, rbx; struct TpmStack *
0x140013d14  call    ?TpmSetDriverState@@YAJPEAVTpmStack@@@Z; TpmSetDriverState(TpmStack *)
0x140013d19  mov     r8d, eax
0x140013d1c  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x140013d23  mov     rdx, r14
0x140013d26  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x140013d2d  mov     rax, [rax+838h]
0x140013d34  call    _guard_dispatch_icall
0x140013d39  mov     rcx, [rbp+var_10]
0x140013d3d  xor     rcx, rsp; StackCookie
0x140013d40  call    __security_check_cookie
0x140013d45  add     rsp, 60h
0x140013d49  pop     r15
0x140013d4b  pop     r14
0x140013d4d  pop     r12
0x140013d4f  pop     rdi
0x140013d50  pop     rsi
0x140013d51  pop     rbx
0x140013d52  pop     rbp
0x140013d53  retn
```
