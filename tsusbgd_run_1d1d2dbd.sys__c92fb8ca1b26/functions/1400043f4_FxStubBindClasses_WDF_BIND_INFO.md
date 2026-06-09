# FxStubBindClasses(_WDF_BIND_INFO *)

- ea: `0x1400043f4`
- end: `0x140004579`
- name: `?FxStubBindClasses@@YAJPEAU_WDF_BIND_INFO@@@Z`
- size: `389`
- prototype: `__int64 __fastcall(struct _WDF_BIND_INFO *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140004244`

## callees

- `0x1400043f4`
- `0x140006370`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x14000442e`
- `ntoskrnl!DbgPrintEx` at `0x1400044e6`
- `ntoskrnl!DbgPrintEx` at `0x14000454e`
- `ntoskrnl!DbgPrintEx` at `0x140004568`
- `ntoskrnl!DbgPrintEx` at `0x14000442e`
- `ntoskrnl!DbgPrintEx` at `0x1400044e6`
- `ntoskrnl!DbgPrintEx` at `0x14000454e`
- `ntoskrnl!DbgPrintEx` at `0x140004568`
- `WDFLDR!WdfVersionBindClass` at `0x140004516`
- `WDFLDR!WdfVersionBindClass` at `0x1400044af`
- `WDFLDR!WdfVersionBindClass` at `0x140004516`

## pseudocode

```c
__int64 __fastcall FxStubBindClasses(struct _WDF_BIND_INFO *a1)
{
  unsigned int v2; // edi
  unsigned int *i; // rax
  unsigned int *v4; // rbx
  unsigned int *j; // rax
  __int64 (__fastcall *v6)(__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD), void *, struct _LIST_ENTRY *, unsigned int *); // rax
  int v7; // eax

  if ( &__KMDF_CLASS_BIND_START <= &__KMDF_CLASS_BIND_END )
  {
    v2 = 0;
    for ( i = (unsigned int *)&__KMDF_CLASS_BIND_END; ; i = (unsigned int *)((char *)v4 + *v4) )
    {
      v4 = i;
      for ( j = i + 2; j <= (unsigned int *)&__KMDF_CLASS_BIND_END && !*(_QWORD *)v4; j = v4 + 2 )
        v4 += 2;
      if ( v4 >= (unsigned int *)&__KMDF_CLASS_BIND_END )
        return v2;
      if ( v4 + 20 > (unsigned int *)&__KMDF_CLASS_BIND_END || *v4 != 80 || !v4 )
        break;
      v6 = (__int64 (__fastcall *)(__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD), void *, struct _LIST_ENTRY *, unsigned int *))*((_QWORD *)v4 + 7);
      off_140009158 = v4;
      if ( v6 )
      {
        v7 = v6(WdfVersionBindClass, &WdfBindInfo, WPP_MAIN_CB.Queue.ListEntry.Blink, v4);
        v2 = v7;
        if ( v7 < 0 )
        {
          DbgPrintEx(
            0x4Du,
            0,
            "FxStubBindClasses: ClientBindClass %p, WDF_CLASS_BIND_INFO 0x%p, class %S, returned status 0x%x\n",
            *((const void **)v4 + 7),
            v4,
            *((const wchar_t **)v4 + 1),
            v7);
          return v2;
        }
      }
      else
      {
        v2 = WdfVersionBindClass(&WdfBindInfo, WPP_MAIN_CB.Queue.ListEntry.Blink, v4);
        if ( (v2 & 0x80000000) != 0 )
        {
          DbgPrintEx(
            0x4Du,
            0,
            "FxStubBindClasses: VersionBindClass WDF_CLASS_BIND_INFO 0x%p, class %S, returned status 0x%x\n",
            v4,
            *((const wchar_t **)v4 + 1),
            v2);
          return v2;
        }
      }
    }
    DbgPrintEx(0x4Du, 0, "FxGetNextClassBindInfo failed\n");
  }
  else
  {
    DbgPrintEx(
      0x4Du,
      0,
      "FxStubBindClasses: invalid driver image, the address of symbol __KMDF_CLASS_BIND_START 0x%p is greater than the ad"
      "dress of symbol __KMDF_CLASS_BIND_END 0x%p, status 0x%x\n",
      &__KMDF_CLASS_BIND_START,
      &__KMDF_CLASS_BIND_END,
      -1073741701);
  }
  return 3221225595LL;
}

```

## disassembly

```asm
0x1400043f4  mov     rax, rsp
0x1400043f7  mov     [rax+8], rbx
0x1400043fb  mov     [rax+10h], rsi
0x1400043ff  push    rdi
0x140004400  sub     rsp, 40h
0x140004404  lea     r9, ?__KMDF_CLASS_BIND_START@@3U_MARKER_TYPE@@A; _MARKER_TYPE __KMDF_CLASS_BIND_START
0x14000440b  lea     rsi, ?__KMDF_CLASS_BIND_END@@3PEAXEA; void * __KMDF_CLASS_BIND_END
0x140004412  cmp     r9, rsi
0x140004415  jbe     short loc_140004444
0x140004417  xor     edx, edx; Level
0x140004419  mov     dword ptr [rax-20h], 0C000007Bh
0x140004420  lea     r8, aFxstubbindclas_1; "FxStubBindClasses: invalid driver image"...
0x140004427  mov     [rax-28h], rsi
0x14000442b  lea     ecx, [rdx+4Dh]; ComponentId
0x14000442e  call    cs:__imp_DbgPrintEx
0x140004435  nop     dword ptr [rax+rax+00h]
0x14000443a  mov     eax, 0C000007Bh
0x14000443f  jmp     loc_1400044F4
0x140004444  xor     edi, edi
0x140004446  lea     rax, ?__KMDF_CLASS_BIND_END@@3PEAXEA; void * __KMDF_CLASS_BIND_END
0x14000444d  mov     rbx, rax
0x140004450  add     rax, 8
0x140004454  jmp     short loc_140004464
0x140004456  cmp     qword ptr [rbx], 0
0x14000445a  jnz     short loc_140004469
0x14000445c  add     rbx, 8
0x140004460  lea     rax, [rbx+8]
0x140004464  cmp     rax, rsi
0x140004467  jbe     short loc_140004456
0x140004469  cmp     rbx, rsi
0x14000446c  jnb     loc_1400044F2
0x140004472  lea     rax, [rbx+50h]
0x140004476  cmp     rax, rsi
0x140004479  ja      loc_14000455C
0x14000447f  cmp     dword ptr [rbx], 50h ; 'P'
0x140004482  jnz     loc_14000455C
0x140004488  test    rbx, rbx
0x14000448b  jz      loc_14000455C
0x140004491  mov     rax, [rbx+38h]
0x140004495  mov     cs:off_140009158, rbx
0x14000449c  test    rax, rax
0x14000449f  jz      short loc_140004505
0x1400044a1  mov     r8, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400044a8  lea     rdx, WdfBindInfo
0x1400044af  mov     rcx, cs:__imp_WdfVersionBindClass
0x1400044b6  mov     r9, rbx
0x1400044b9  call    _guard_dispatch_icall
0x1400044be  mov     edi, eax
0x1400044c0  test    eax, eax
0x1400044c2  jns     short loc_140004528
0x1400044c4  mov     r9, [rbx+38h]
0x1400044c8  lea     r8, aFxstubbindclas; "FxStubBindClasses: ClientBindClass %p, "...
0x1400044cf  mov     [rsp+48h+var_18], eax
0x1400044d3  xor     edx, edx; Level
0x1400044d5  mov     rax, [rbx+8]
0x1400044d9  mov     [rsp+48h+var_20], rax
0x1400044de  mov     [rsp+48h+var_28], rbx
0x1400044e3  lea     ecx, [rdx+4Dh]; ComponentId
0x1400044e6  call    cs:__imp_DbgPrintEx
0x1400044ed  nop     dword ptr [rax+rax+00h]
0x1400044f2  mov     eax, edi
0x1400044f4  mov     rbx, [rsp+48h+arg_0]
0x1400044f9  mov     rsi, [rsp+48h+arg_8]
0x1400044fe  add     rsp, 40h
0x140004502  pop     rdi
0x140004503  retn
0x140004505  mov     rdx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000450c  lea     rcx, WdfBindInfo
0x140004513  mov     r8, rbx
0x140004516  call    cs:__imp_WdfVersionBindClass
0x14000451d  nop     dword ptr [rax+rax+00h]
0x140004522  mov     edi, eax
0x140004524  test    eax, eax
0x140004526  js      short loc_140004532
0x140004528  mov     eax, [rbx]
0x14000452a  add     rax, rbx
0x14000452d  jmp     loc_14000444D
0x140004532  mov     rax, [rbx+8]
0x140004536  lea     r8, aFxstubbindclas_0; "FxStubBindClasses: VersionBindClass WDF"...
0x14000453d  xor     edx, edx; Level
0x14000453f  mov     dword ptr [rsp+48h+var_20], edi
0x140004543  mov     r9, rbx
0x140004546  mov     [rsp+48h+var_28], rax
0x14000454b  lea     ecx, [rdx+4Dh]; ComponentId
0x14000454e  call    cs:__imp_DbgPrintEx
0x140004555  nop     dword ptr [rax+rax+00h]
0x14000455a  jmp     short loc_1400044F2
0x14000455c  xor     edx, edx; Level
0x14000455e  lea     r8, Format; "FxGetNextClassBindInfo failed\n"
0x140004565  lea     ecx, [rdx+4Dh]; ComponentId
0x140004568  call    cs:__imp_DbgPrintEx
0x14000456f  nop     dword ptr [rax+rax+00h]
0x140004574  jmp     loc_14000443A
```
