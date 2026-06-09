# Windows::Telemetry::Base::PreventSleep::StartActivity(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800529c0`
- end: `0x180052b85`
- name: `?StartActivity@PreventSleep@Base@Telemetry@Windows@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `453`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18004fc28`

## callees

- `0x1800019cc`
- `0x180007660`
- `0x180016180`
- `0x180041c1c`
- `0x1800445d4`
- `0x1800529c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180052a47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180052b5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180052a47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180052b5b`

## pseudocode

```c
int __fastcall Windows::Telemetry::Base::PreventSleep::StartActivity(__int64 a1, const wchar_t *a2, const wchar_t *a3)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r14
  __int64 Local; // rax
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  int v12; // r9d
  __int64 v13; // rax
  int v14; // edx
  __int64 v15; // rcx
  int v16; // ecx
  __int64 *v17; // rbx
  DWORD v19; // [rsp+30h] [rbp-59h] BYREF
  __int64 v20; // [rsp+38h] [rbp-51h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v21; // [rsp+40h] [rbp-49h] BYREF
  __int64 *v22; // [rsp+60h] [rbp-29h]
  __int64 v23; // [rsp+68h] [rbp-21h]
  DWORD *v24; // [rsp+70h] [rbp-19h]
  __int64 v25; // [rsp+78h] [rbp-11h]
  const wchar_t *v26; // [rsp+80h] [rbp-9h]
  int v27; // [rsp+88h] [rbp-1h]
  int v28; // [rsp+8Ch] [rbp+3h]
  const wchar_t *v29; // [rsp+90h] [rbp+7h]
  int v30; // [rsp+98h] [rbp+Fh]
  int v31; // [rsp+9Ch] [rbp+13h]

  wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v8 = *((_QWORD *)Windows::Telemetry::Base::Instance() + 1);
  LODWORD(Local) = *(_DWORD *)v8;
  if ( *(_DWORD *)v8 > 5u )
  {
    v7 = *(_QWORD *)(v8 + 24);
    v6 = 0x400000000000LL;
    Local = *(_QWORD *)(v8 + 16);
    if ( (Local & 0x400000000000LL) != 0 )
    {
      LODWORD(Local) = 0;
      if ( (v7 & 0x400000000000LL) == v7 )
      {
        if ( *((_QWORD *)a3 + 3) > 7u )
          a3 = *(const wchar_t **)a3;
        if ( *((_QWORD *)a2 + 3) > 7u )
          a2 = *(const wchar_t **)a2;
        CurrentThreadId = GetCurrentThreadId();
        v11 = *(_QWORD *)(a1 + 272);
        v19 = CurrentThreadId;
        v20 = 0x1000000;
        if ( !*(_BYTE *)(v11 + 4)
          || (v12 = v11 + 24, !*(_DWORD *)(v11 + 24))
          && !*(_DWORD *)(v11 + 28)
          && !*(_DWORD *)(v11 + 32)
          && !*(_DWORD *)(v11 + 36) )
        {
          v12 = 0;
        }
        v13 = -1;
        v14 = 2;
        if ( a3 )
        {
          v15 = -1;
          do
            ++v15;
          while ( a3[v15] );
          v16 = 2 * v15 + 2;
        }
        else
        {
          a3 = &psz;
          v16 = 2;
        }
        v29 = a3;
        v30 = v16;
        v31 = 0;
        if ( a2 )
        {
          do
            ++v13;
          while ( a2[v13] );
          v14 = 2 * v13 + 2;
        }
        else
        {
          a2 = &psz;
        }
        v27 = v14;
        v24 = &v19;
        v26 = a2;
        v22 = &v20;
        v28 = 0;
        v25 = 4;
        v23 = 8;
        LODWORD(Local) = tlgWriteTransfer_EventWriteTransfer(v8, (int)&dword_1800826E4, (int)v11 + 8, v12, 6u, &v21);
      }
    }
  }
  if ( !*(_DWORD *)(a1 + 312) )
  {
    v17 = (__int64 *)(a1 + 288);
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      LOBYTE(v6) = 1;
      Local = wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(v7, v6);
      *v17 = Local;
      if ( Local )
      {
        *(_QWORD *)(a1 + 304) = *(_QWORD *)Local;
        *(_QWORD *)Local = v17;
        LODWORD(Local) = GetCurrentThreadId();
        *(_DWORD *)(a1 + 312) = Local;
      }
    }
    else
    {
      *v17 = 0;
    }
  }
  return Local;
}

```

## disassembly

```asm
0x1800529c0  push    rbp
0x1800529c2  push    rbx
0x1800529c3  push    rsi
0x1800529c4  push    rdi
0x1800529c5  push    r14
0x1800529c7  push    r15
0x1800529c9  lea     rbp, [rsp-2Fh]
0x1800529ce  sub     rsp, 0B8h
0x1800529d5  mov     rax, cs:__security_cookie
0x1800529dc  xor     rax, rsp
0x1800529df  mov     [rbp+57h+var_40], rax
0x1800529e3  mov     rbx, r8
0x1800529e6  mov     rdi, rdx
0x1800529e9  mov     rsi, rcx
0x1800529ec  call    ?zInternalStart@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800529f1  call    ?Instance@Base@Telemetry@Windows@@KAPEAV123@XZ; Windows::Telemetry::Base::Instance(void)
0x1800529f6  xor     r15d, r15d
0x1800529f9  mov     r14, [rax+8]
0x1800529fd  mov     eax, [r14]
0x180052a00  cmp     eax, 5
0x180052a03  jbe     loc_180052B29
0x180052a09  mov     rcx, [r14+18h]
0x180052a0d  mov     rdx, 400000000000h
0x180052a17  mov     rax, [r14+10h]
0x180052a1b  test    rdx, rax
0x180052a1e  jz      loc_180052B29
0x180052a24  mov     rax, rcx
0x180052a27  and     rax, rdx
0x180052a2a  cmp     rax, rcx
0x180052a2d  jnz     loc_180052B29
0x180052a33  cmp     qword ptr [rbx+18h], 7
0x180052a38  jbe     short loc_180052A3D
0x180052a3a  mov     rbx, [rbx]
0x180052a3d  cmp     qword ptr [rdi+18h], 7
0x180052a42  jbe     short loc_180052A47
0x180052a44  mov     rdi, [rdi]
0x180052a47  call    cs:__imp_GetCurrentThreadId
0x180052a4d  mov     r8, [rsi+110h]
0x180052a54  mov     [rbp+57h+var_B0], eax
0x180052a57  mov     [rbp+57h+var_A8], 1000000h
0x180052a5f  cmp     [r8+4], r15b
0x180052a63  jz      short loc_180052A80
0x180052a65  lea     r9, [r8+18h]
0x180052a69  cmp     [r9], r15d
0x180052a6c  jnz     short loc_180052A83
0x180052a6e  cmp     [r9+4], r15d
0x180052a72  jnz     short loc_180052A83
0x180052a74  cmp     [r9+8], r15d
0x180052a78  jnz     short loc_180052A83
0x180052a7a  cmp     [r9+0Ch], r15d
0x180052a7e  jnz     short loc_180052A83
0x180052a80  mov     r9, r15; int
0x180052a83  or      rax, 0FFFFFFFFFFFFFFFFh
0x180052a87  mov     edx, 2
0x180052a8c  test    rbx, rbx
0x180052a8f  jz      short loc_180052AA7
0x180052a91  mov     rcx, rax
0x180052a94  inc     rcx
0x180052a97  cmp     [rbx+rcx*2], r15w
0x180052a9c  jnz     short loc_180052A94
0x180052a9e  lea     ecx, ds:2[rcx*2]
0x180052aa5  jmp     short loc_180052AB0
0x180052aa7  lea     rbx, psz
0x180052aae  mov     ecx, edx
0x180052ab0  mov     [rbp+57h+var_50], rbx
0x180052ab4  mov     [rbp+57h+var_48], ecx
0x180052ab7  mov     [rbp+57h+var_44], r15d
0x180052abb  test    rdi, rdi
0x180052abe  jz      short loc_180052AD3
0x180052ac0  inc     rax
0x180052ac3  cmp     [rdi+rax*2], r15w
0x180052ac8  jnz     short loc_180052AC0
0x180052aca  lea     edx, ds:2[rax*2]
0x180052ad1  jmp     short loc_180052ADA
0x180052ad3  lea     rdi, psz
0x180052ada  lea     rax, [rbp+57h+var_B0]
0x180052ade  mov     [rbp+57h+var_58], edx
0x180052ae1  mov     [rbp+57h+var_70], rax
0x180052ae5  lea     rdx, dword_1800826E4; int
0x180052aec  lea     rax, [rbp+57h+var_A8]
0x180052af0  mov     [rbp+57h+var_60], rdi
0x180052af4  mov     [rbp+57h+var_80], rax
0x180052af8  add     r8, 8; int
0x180052afc  lea     rax, [rbp+57h+var_A0]
0x180052b00  mov     [rbp+57h+var_54], r15d
0x180052b04  mov     [rsp+0E0h+var_B8], rax; PEVENT_DATA_DESCRIPTOR
0x180052b09  mov     rcx, r14; int
0x180052b0c  mov     [rsp+0E0h+var_C0], 6; ULONG
0x180052b14  mov     [rbp+57h+var_68], 4
0x180052b1c  mov     [rbp+57h+var_78], 8
0x180052b24  call    _tlgWriteTransfer_EventWriteTransfer
0x180052b29  cmp     [rsi+138h], r15d
0x180052b30  jnz     short loc_180052B69
0x180052b32  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r15; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180052b39  lea     rbx, [rsi+120h]
0x180052b40  jz      short loc_180052B66
0x180052b42  mov     dl, 1
0x180052b44  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180052b49  mov     [rbx], rax
0x180052b4c  test    rax, rax
0x180052b4f  jz      short loc_180052B69
0x180052b51  mov     rcx, [rax]
0x180052b54  mov     [rbx+10h], rcx
0x180052b58  mov     [rax], rbx
0x180052b5b  call    cs:__imp_GetCurrentThreadId
0x180052b61  mov     [rbx+18h], eax
0x180052b64  jmp     short loc_180052B69
0x180052b66  mov     [rbx], r15
0x180052b69  mov     rcx, [rbp+57h+var_40]
0x180052b6d  xor     rcx, rsp; StackCookie
0x180052b70  call    __security_check_cookie
0x180052b75  add     rsp, 0B8h
0x180052b7c  pop     r15
0x180052b7e  pop     r14
0x180052b80  pop     rdi
0x180052b81  pop     rsi
0x180052b82  pop     rbx
0x180052b83  pop     rbp
0x180052b84  retn
```
