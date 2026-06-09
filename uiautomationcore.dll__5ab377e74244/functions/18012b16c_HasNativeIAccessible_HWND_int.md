# HasNativeIAccessible(HWND__ *,int *)

- ea: `0x18012b16c`
- end: `0x18012b29b`
- name: `?HasNativeIAccessible@@YAJPEAUHWND__@@PEAH@Z`
- size: `303`
- prototype: `__int64 __fastcall(HWND, int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18012ac64`
- `0x18012af74`

## callees

- `0x18000f680`
- `0x1800db24c`
- `0x18012b16c`
- `0x1801334b8`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18012b1a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18012b1a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18012b1b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18012b1b3`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x18012b19a`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x18012b19a`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsWindow` at `0x18012b187`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsWindow` at `0x18012b187`
- `OLEACC!ObjectFromLresult` at `0x18012b257`
- `OLEACC!ObjectFromLresult` at `0x18012b257`

## string_xrefs

- `0x18012b21a`: `HasNativeIAccessible`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HasNativeIAccessible(HWND a1, int *a2)
{
  DWORD WindowThreadProcessId; // ebx
  unsigned __int64 v5; // rbx
  __int64 CurrentProcessId; // rcx
  int v7; // edi
  LONG_PTR v9; // rcx
  HRESULT v10; // ebx
  void *v11; // rcx
  void *ppvObject; // [rsp+58h] [rbp+28h] BYREF
  __int64 v13; // [rsp+60h] [rbp+30h] BYREF

  *a2 = 0;
  if ( IsWindow(a1) )
  {
    WindowThreadProcessId = GetWindowThreadProcessId(a1, 0);
    if ( WindowThreadProcessId == GetCurrentThreadId() )
    {
      v5 = 0xFFFFFFFFLL;
    }
    else
    {
      CurrentProcessId = GetCurrentProcessId();
      if ( CurrentProcessId == 0xFFFFFFFFLL )
        LODWORD(CurrentProcessId) = 0;
      v5 = (unsigned int)CurrentProcessId;
    }
    v13 = 0;
    LOBYTE(ppvObject) = 1;
    *(_WORD *)((char *)&ppvObject + 1) = 0;
    BYTE3(ppvObject) = 0;
    HIDWORD(ppvObject) = 2000;
    v7 = BasicHwndUtils::UIASendMessageTimeout((const struct UIA_TIMEOUTDATA *)&ppvObject, a1, 0x3Du, v5, -4, &v13);
    if ( v7 < 0 )
    {
      Error::Win32Error(L"HasNativeIAccessible", L"Call to SendMessageTimeout failed");
      return (unsigned int)v7;
    }
    v9 = v13;
  }
  else
  {
    v9 = 0;
    v5 = 0;
  }
  if ( (int)v9 < 0 )
    return (unsigned int)v9;
  if ( v9 )
  {
    ppvObject = 0;
    v10 = ObjectFromLresult(v9, &IID_IAccessible, v5, &ppvObject);
    if ( v10 >= 0 )
    {
      v11 = ppvObject;
      if ( ppvObject )
      {
        *a2 = 1;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11);
        return (unsigned int)v10;
      }
    }
    wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&ppvObject);
  }
  return 0;
}

```

## disassembly

```asm
0x18012b16c  mov     [rsp-18h+arg_0], rbx
0x18012b171  push    rbp
0x18012b172  push    rsi
0x18012b173  push    rdi
0x18012b174  mov     rbp, rsp
0x18012b177  sub     rsp, 30h
0x18012b17b  mov     rsi, rdx
0x18012b17e  mov     rdi, rcx
0x18012b181  mov     dword ptr [rdx], 0
0x18012b187  call    cs:__imp_IsWindow
0x18012b18d  test    eax, eax
0x18012b18f  jz      loc_18012B230
0x18012b195  xor     edx, edx; lpdwProcessId
0x18012b197  mov     rcx, rdi; hWnd
0x18012b19a  call    cs:__imp_GetWindowThreadProcessId
0x18012b1a0  mov     ebx, eax
0x18012b1a2  call    cs:__imp_GetCurrentThreadId
0x18012b1a8  cmp     ebx, eax
0x18012b1aa  jnz     short loc_18012B1B3
0x18012b1ac  mov     ebx, 0FFFFFFFFh
0x18012b1b1  jmp     short loc_18012B1CA
0x18012b1b3  call    cs:__imp_GetCurrentProcessId
0x18012b1b9  mov     ecx, eax
0x18012b1bb  xor     eax, eax
0x18012b1bd  mov     ebx, 0FFFFFFFFh
0x18012b1c2  cmp     rcx, rbx
0x18012b1c5  cmovz   ecx, eax
0x18012b1c8  mov     ebx, ecx
0x18012b1ca  mov     [rbp+arg_10], 0
0x18012b1d2  mov     byte ptr [rbp+ppvObject], 1
0x18012b1d6  xor     eax, eax
0x18012b1d8  mov     word ptr [rbp+ppvObject+1], ax
0x18012b1dc  mov     byte ptr [rbp+ppvObject+3], al
0x18012b1df  mov     dword ptr [rbp+ppvObject+4], 7D0h
0x18012b1e6  lea     rax, [rbp+arg_10]
0x18012b1ea  mov     [rsp+30h+var_8], rax; __int64 *
0x18012b1ef  mov     [rsp+30h+var_10], 0FFFFFFFFFFFFFFFCh; __int64
0x18012b1f8  mov     r9, rbx; unsigned __int64
0x18012b1fb  mov     r8d, 3Dh ; '='; unsigned int
0x18012b201  mov     rdx, rdi; HWND
0x18012b204  lea     rcx, [rbp+ppvObject]; struct UIA_TIMEOUTDATA *
0x18012b208  call    ?UIASendMessageTimeout@BasicHwndUtils@@SAJAEBUUIA_TIMEOUTDATA@@PEAUHWND__@@I_K_JPEA_J@Z; BasicHwndUtils::UIASendMessageTimeout(UIA_TIMEOUTDATA const &,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x18012b20d  mov     edi, eax
0x18012b20f  test    eax, eax
0x18012b211  jns     short loc_18012B22A
0x18012b213  lea     rdx, aCallToSendmess; "Call to SendMessageTimeout failed"
0x18012b21a  lea     rcx, aHasnativeiacce; "HasNativeIAccessible"
0x18012b221  call    ?Win32Error@Error@@SAJPEBG0@Z; Error::Win32Error(ushort const *,ushort const *)
0x18012b226  mov     eax, edi
0x18012b228  jmp     short loc_18012B28E
0x18012b22a  mov     rcx, [rbp+arg_10]
0x18012b22e  jmp     short loc_18012B234
0x18012b230  xor     ecx, ecx; lResult
0x18012b232  xor     ebx, ebx
0x18012b234  test    ecx, ecx
0x18012b236  jns     short loc_18012B23C
0x18012b238  mov     eax, ecx
0x18012b23a  jmp     short loc_18012B28E
0x18012b23c  test    rcx, rcx
0x18012b23f  jz      short loc_18012B28C
0x18012b241  mov     [rbp+ppvObject], 0
0x18012b249  lea     r9, [rbp+ppvObject]; ppvObject
0x18012b24d  mov     r8, rbx; wParam
0x18012b250  lea     rdx, IID_IAccessible; riid
0x18012b257  call    cs:__imp_ObjectFromLresult
0x18012b25d  mov     ebx, eax
0x18012b25f  test    eax, eax
0x18012b261  js      short loc_18012B283
0x18012b263  mov     rcx, [rbp+ppvObject]
0x18012b267  test    rcx, rcx
0x18012b26a  jz      short loc_18012B283
0x18012b26c  mov     dword ptr [rsi], 1
0x18012b272  mov     rdx, [rcx]
0x18012b275  mov     rax, [rdx+10h]
0x18012b279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012b27e  nop
0x18012b27f  mov     eax, ebx
0x18012b281  jmp     short loc_18012B28E
0x18012b283  lea     rcx, [rbp+ppvObject]; void *
0x18012b287  call    ??1?$com_ptr_t@UIAccessibleAction@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(void)
0x18012b28c  xor     eax, eax
0x18012b28e  mov     rbx, [rsp+30h+arg_0]
0x18012b293  add     rsp, 30h
0x18012b297  pop     rdi
0x18012b298  pop     rsi
0x18012b299  pop     rbp
0x18012b29a  retn
```
