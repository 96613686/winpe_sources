# _CreatePWSTRFromUSTRAlloc(_UNICODE_STRING const *,ushort * *)

- ea: `0x180014030`
- end: `0x1800140a3`
- name: `?_CreatePWSTRFromUSTRAlloc@@YAJPEBU_UNICODE_STRING@@PEAPEAG@Z`
- size: `115`
- prototype: `__int64 __fastcall(const struct _UNICODE_STRING *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800063b0`

## callees

- `0x180009430`
- `0x180014030`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014092`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014092`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014061`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014061`

## pseudocode

```c
__int64 __fastcall _CreatePWSTRFromUSTRAlloc(const struct _UNICODE_STRING *a1, unsigned __int16 **a2)
{
  int v4; // edi
  SIZE_T v5; // rcx
  unsigned __int16 *v6; // rax
  unsigned __int16 *v7; // rbx

  v4 = -2147467261;
  if ( a1 )
  {
    if ( a2 )
    {
      v4 = -2147024882;
      v5 = a1->Length + 2LL;
      *a2 = 0;
      v6 = (unsigned __int16 *)CoTaskMemAlloc(v5);
      v7 = v6;
      if ( v6 )
      {
        v4 = StringCbCopyNW(v6, a1->Length + 2LL, a1->Buffer, a1->Length);
        if ( v4 >= 0 )
        {
          *a2 = v7;
          v7 = 0;
        }
        CoTaskMemFree(v7);
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180014030  push    rbx
0x180014032  push    rbp
0x180014033  push    rsi
0x180014034  push    rdi
0x180014035  sub     rsp, 28h
0x180014039  mov     rsi, rdx
0x18001403c  mov     rbp, rcx
0x18001403f  mov     edi, 80004003h
0x180014044  test    rcx, rcx
0x180014047  jz      short loc_180014098
0x180014049  test    rdx, rdx
0x18001404c  jz      short loc_180014098
0x18001404e  movzx   ecx, word ptr [rcx]
0x180014051  mov     edi, 8007000Eh
0x180014056  add     rcx, 2; cb
0x18001405a  mov     qword ptr [rdx], 0
0x180014061  call    cs:__imp_CoTaskMemAlloc
0x180014067  mov     rbx, rax
0x18001406a  test    rax, rax
0x18001406d  jz      short loc_180014098
0x18001406f  movzx   r9d, word ptr [rbp+0]; unsigned __int64
0x180014074  mov     rcx, rax; unsigned __int16 *
0x180014077  mov     r8, [rbp+8]; unsigned __int16 *
0x18001407b  lea     rdx, [r9+2]; unsigned __int64
0x18001407f  call    ?StringCbCopyNW@@YAJPEAG_KPEBG1@Z; StringCbCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180014084  mov     edi, eax
0x180014086  test    eax, eax
0x180014088  js      short loc_18001408F
0x18001408a  mov     [rsi], rbx
0x18001408d  xor     ebx, ebx
0x18001408f  mov     rcx, rbx; pv
0x180014092  call    cs:__imp_CoTaskMemFree
0x180014098  mov     eax, edi
0x18001409a  add     rsp, 28h
0x18001409e  pop     rdi
0x18001409f  pop     rsi
0x1800140a0  pop     rbp
0x1800140a1  pop     rbx
0x1800140a2  retn
```
