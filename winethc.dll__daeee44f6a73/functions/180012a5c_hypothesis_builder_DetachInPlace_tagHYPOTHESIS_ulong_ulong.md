# _hypothesis_builder::DetachInPlace(tagHYPOTHESIS &,ulong *,ulong *)

- ea: `0x180012a5c`
- end: `0x180012b08`
- name: `?DetachInPlace@_hypothesis_builder@@IEAAJAEAUtagHYPOTHESIS@@PEAK1@Z`
- size: `172`
- prototype: `__int64 __fastcall(_hypothesis_builder *__hidden this, struct tagHYPOTHESIS *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012794`

## callees

- `0x180012a5c`
- `0x180012b10`
- `0x180012ca0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012a9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012a9d`

## pseudocode

```c
__int64 __fastcall _hypothesis_builder::DetachInPlace(
        WCHAR **this,
        struct tagHYPOTHESIS *a2,
        unsigned int *a3,
        unsigned int *a4)
{
  _OWORD *v8; // rcx
  WCHAR *v9; // rax
  LPVOID pv; // [rsp+60h] [rbp+18h] BYREF

  pv = 0;
  _hypothesis_builder::DoDetach((_hypothesis_builder *)this, (struct tagHYPOTHESIS **)&pv);
  v8 = pv;
  if ( pv )
  {
    *(_OWORD *)&a2->pwszClassName = *(_OWORD *)pv;
    *(_OWORD *)&a2->celt = v8[1];
    CoTaskMemFree(v8);
  }
  else
  {
    if ( *((_DWORD *)this + 4) || this[3] )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    a2->pwszClassName = *this;
    v9 = this[1];
    *this = 0;
    a2->pwszDescription = v9;
    this[1] = 0;
    a2->celt = 0;
    a2->rgAttributes = 0;
  }
  *a3 = 1;
  if ( a4 )
    *a4 = 32;
  return 0;
}

```

## disassembly

```asm
0x180012a5c  push    rbx
0x180012a5e  push    rsi
0x180012a5f  push    rdi
0x180012a60  push    r14
0x180012a62  sub     rsp, 28h
0x180012a66  mov     rdi, rdx
0x180012a69  mov     [rsp+48h+pv], 0
0x180012a72  lea     rdx, [rsp+48h+pv]; struct tagHYPOTHESIS **
0x180012a77  mov     rsi, r9
0x180012a7a  mov     r14, r8
0x180012a7d  mov     rbx, rcx
0x180012a80  call    ?DoDetach@_hypothesis_builder@@IEAAXPEAPEAUtagHYPOTHESIS@@@Z; _hypothesis_builder::DoDetach(tagHYPOTHESIS * *)
0x180012a85  mov     rcx, [rsp+48h+pv]; pv
0x180012a8a  test    rcx, rcx
0x180012a8d  jz      short loc_180012AAB
0x180012a8f  movups  xmm0, xmmword ptr [rcx]
0x180012a92  movups  xmmword ptr [rdi], xmm0
0x180012a95  movups  xmm1, xmmword ptr [rcx+10h]
0x180012a99  movups  xmmword ptr [rdi+10h], xmm1
0x180012a9d  call    cs:__imp_CoTaskMemFree
0x180012aa4  nop     dword ptr [rax+rax+00h]
0x180012aa9  jmp     short loc_180012AE9
0x180012aab  cmp     dword ptr [rbx+10h], 0
0x180012aaf  jnz     short loc_180012AB8
0x180012ab1  cmp     qword ptr [rbx+18h], 0
0x180012ab6  jz      short loc_180012ABD
0x180012ab8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180012abd  mov     rax, [rbx]
0x180012ac0  mov     [rdi], rax
0x180012ac3  mov     rax, [rbx+8]
0x180012ac7  mov     qword ptr [rbx], 0
0x180012ace  mov     [rdi+8], rax
0x180012ad2  mov     qword ptr [rbx+8], 0
0x180012ada  mov     dword ptr [rdi+10h], 0
0x180012ae1  mov     qword ptr [rdi+18h], 0
0x180012ae9  mov     dword ptr [r14], 1
0x180012af0  test    rsi, rsi
0x180012af3  jz      short loc_180012AFB
0x180012af5  mov     dword ptr [rsi], 20h ; ' '
0x180012afb  xor     eax, eax
0x180012afd  add     rsp, 28h
0x180012b01  pop     r14
0x180012b03  pop     rdi
0x180012b04  pop     rsi
0x180012b05  pop     rbx
0x180012b06  retn
```
