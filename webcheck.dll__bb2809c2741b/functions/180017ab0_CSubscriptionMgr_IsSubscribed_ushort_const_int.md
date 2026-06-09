# CSubscriptionMgr::IsSubscribed(ushort const *,int *)

- ea: `0x180017ab0`
- end: `0x180017b48`
- name: `?IsSubscribed@CSubscriptionMgr@@UEAAJPEBGPEAH@Z`
- size: `152`
- prototype: `int(CSubscriptionMgr *__hidden this, const unsigned __int16 *, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003950`
- `0x18000e28c`
- `0x180017ab0`

## import_xrefs

- `SHLWAPI!UrlCompareW` at `0x180017b2c`
- `SHLWAPI!UrlCompareW` at `0x180017b2c`
- `ole32!CoTaskMemFree` at `0x180017b39`
- `ole32!CoTaskMemFree` at `0x180017b39`

## pseudocode

```c
__int64 __fastcall CSubscriptionMgr::IsSubscribed(CSubscriptionMgr *this, const unsigned __int16 *a2, int *a3)
{
  const WCHAR *v4; // rdi
  LPVOID *v5; // rbx

  v4 = (const WCHAR *)((char *)this + 48);
  v5 = (LPVOID *)((char *)this + 24);
  StringCchCopyW((unsigned __int16 *)this + 24, 0x824u, a2);
  *a3 = 0;
  if ( *v5 )
  {
    if ( !UrlCompareW((PCWSTR)((char *)*v5 + *((_QWORD *)*v5 + 25) + 8), v4, 1) )
    {
LABEL_4:
      *a3 = 1;
      return 0;
    }
    CoTaskMemFree(*v5);
    *v5 = 0;
  }
  if ( !(unsigned int)LoadSubscription(v4, v5) && *v5 )
    goto LABEL_4;
  return 0;
}

```

## disassembly

```asm
0x180017ab0  mov     [rsp+arg_0], rbx
0x180017ab5  mov     [rsp+arg_8], rsi
0x180017aba  push    rdi
0x180017abb  sub     rsp, 20h
0x180017abf  mov     rsi, r8
0x180017ac2  lea     rdi, [rcx+30h]
0x180017ac6  mov     r8, rdx; unsigned __int16 *
0x180017ac9  lea     rbx, [rcx+18h]
0x180017acd  mov     edx, 824h; unsigned __int64
0x180017ad2  mov     rcx, rdi; unsigned __int16 *
0x180017ad5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017ada  mov     dword ptr [rsi], 0
0x180017ae0  mov     rcx, [rbx]
0x180017ae3  test    rcx, rcx
0x180017ae6  jnz     short loc_180017B15
0x180017ae8  mov     rdx, rbx
0x180017aeb  mov     rcx, rdi
0x180017aee  call    LoadSubscription
0x180017af3  test    eax, eax
0x180017af5  jnz     short loc_180017B03
0x180017af7  cmp     qword ptr [rbx], 0
0x180017afb  jz      short loc_180017B03
0x180017afd  mov     dword ptr [rsi], 1
0x180017b03  mov     rbx, [rsp+28h+arg_0]
0x180017b08  xor     eax, eax
0x180017b0a  mov     rsi, [rsp+28h+arg_8]
0x180017b0f  add     rsp, 20h
0x180017b13  pop     rdi
0x180017b14  retn
0x180017b15  mov     rax, [rcx+0C8h]
0x180017b1c  mov     r8d, 1; fIgnoreSlash
0x180017b22  add     rcx, 8
0x180017b26  mov     rdx, rdi; psz2
0x180017b29  add     rcx, rax; psz1
0x180017b2c  call    cs:__imp_UrlCompareW
0x180017b32  test    eax, eax
0x180017b34  jz      short loc_180017AFD
0x180017b36  mov     rcx, [rbx]; pv
0x180017b39  call    cs:__imp_CoTaskMemFree
0x180017b3f  mov     qword ptr [rbx], 0
0x180017b46  jmp     short loc_180017AE8
```
