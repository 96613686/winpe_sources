# JsonHelper::NonDelegatingQueryInterface(_GUID const &,void * *)

- ea: `0x1800138b0`
- end: `0x180013914`
- name: `?NonDelegatingQueryInterface@JsonHelper@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `100`
- prototype: `__int64 __fastcall(JsonHelper *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180010c20`
- `0x1800138b0`
- `0x180016010`

## pseudocode

```c
__int64 __fastcall JsonHelper::NonDelegatingQueryInterface(JsonHelper *this, const struct _GUID *a2, void **a3)
{
  __int64 v3; // rax
  __int64 v4; // rax
  char *v5; // rcx

  v3 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
    v3 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IUnknown.Data4;
  if ( !v3 )
  {
    CTSUnknown::NonDelegatingQueryInterface(this, a2, a3);
    return 0;
  }
  v4 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IJsonHelper.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IJsonHelper.Data1 )
    v4 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IJsonHelper.Data4;
  if ( !v4 )
  {
    v5 = (char *)this - 8;
    *a3 = v5;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v5 + 8LL))(v5);
    return 0;
  }
  return 2147500034LL;
}

```

## disassembly

```asm
0x1800138b0  sub     rsp, 28h
0x1800138b4  mov     rax, [rdx]
0x1800138b7  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x1800138be  jnz     short loc_1800138CB
0x1800138c0  mov     rax, [rdx+8]
0x1800138c4  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x1800138cb  test    rax, rax
0x1800138ce  jnz     short loc_1800138D7
0x1800138d0  call    ?NonDelegatingQueryInterface@CTSUnknown@@UEAAJAEBU_GUID@@PEAPEAX@Z; CTSUnknown::NonDelegatingQueryInterface(_GUID const &,void * *)
0x1800138d5  jmp     short loc_180013906
0x1800138d7  mov     rax, [rdx]
0x1800138da  sub     rax, qword ptr cs:IID_IJsonHelper.Data1
0x1800138e1  jnz     short loc_1800138EE
0x1800138e3  mov     rax, [rdx+8]
0x1800138e7  sub     rax, qword ptr cs:IID_IJsonHelper.Data4
0x1800138ee  test    rax, rax
0x1800138f1  jnz     short loc_18001390A
0x1800138f3  add     rcx, 0FFFFFFFFFFFFFFF8h
0x1800138f7  mov     [r8], rcx
0x1800138fa  mov     rax, [rcx]
0x1800138fd  mov     rax, [rax+8]
0x180013901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013906  xor     eax, eax
0x180013908  jmp     short loc_18001390F
0x18001390a  mov     eax, 80004002h
0x18001390f  add     rsp, 28h
0x180013913  retn
```
