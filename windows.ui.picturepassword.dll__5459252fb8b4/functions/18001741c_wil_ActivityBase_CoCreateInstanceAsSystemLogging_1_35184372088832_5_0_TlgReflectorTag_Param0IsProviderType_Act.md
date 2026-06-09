# wil::ActivityBase<CoCreateInstanceAsSystemLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CoCreateInstanceAsSystemLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)

- ea: `0x18001741c`
- end: `0x1800174d2`
- name: `??0?$ActivityBase@VCoCreateInstanceAsSystemLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z`
- size: `182`
- prototype: `struct wil::details::IFailureCallback *__fastcall(struct wil::details::IFailureCallback *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800185b4`

## callees

- `0x180002f94`
- `0x180005910`

## string_xrefs

- `0x18001744d`: `CoCreateInstanceAsSystem`

## pseudocode

```c
struct wil::details::IFailureCallback *__fastcall wil::ActivityBase<CoCreateInstanceAsSystemLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CoCreateInstanceAsSystemLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
        struct wil::details::IFailureCallback *a1)
{
  char *v1; // rbx
  _QWORD *v3; // rcx

  v1 = (char *)a1 + 8;
  *(_QWORD *)a1 = &wil::ActivityBase<CoCreateInstanceAsSystemLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::`vftable';
  *((_DWORD *)a1 + 2) = 0;
  v3 = (_QWORD *)((char *)a1 + 88);
  v1[4] = 0;
  *((_QWORD *)v1 + 6) = "CoCreateInstanceAsSystem";
  v1[64] = 0;
  *((_DWORD *)v1 + 10) = 0;
  *((_QWORD *)v1 + 7) = 0;
  *((_DWORD *)v1 + 18) = 0;
  v3[19] = 0;
  v3[20] = 0;
  memset_0(v3, 0, 0x98u);
  *((_DWORD *)v1 + 62) = 1;
  *((_QWORD *)v1 + 32) = 0;
  *((_QWORD *)a1 + 34) = v1;
  *((_QWORD *)a1 + 35) = 0;
  wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
    (struct wil::details::IFailureCallback *)((char *)a1 + 288),
    a1,
    (struct wil::details::IFailureCallback *)((char *)a1 + 48),
    0);
  return a1;
}

```

## disassembly

```asm
0x18001741c  mov     [rsp+arg_0], rbx
0x180017421  push    rdi
0x180017422  sub     rsp, 20h
0x180017426  lea     rbx, [rcx+8]
0x18001742a  mov     rdi, rcx
0x18001742d  lea     rax, ??_7?$ActivityBase@VCoCreateInstanceAsSystemLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@6B@; const wil::ActivityBase<CoCreateInstanceAsSystemLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::`vftable'
0x180017434  xor     edx, edx; Val
0x180017436  mov     [rcx], rax
0x180017439  mov     r8d, 98h; Size
0x18001743f  mov     dword ptr [rbx], 0
0x180017445  lea     rcx, [rbx+50h]; void *
0x180017449  mov     byte ptr [rbx+4], 0
0x18001744d  lea     rax, aCocreateinstan; "CoCreateInstanceAsSystem"
0x180017454  mov     [rbx+30h], rax
0x180017458  mov     byte ptr [rbx+40h], 0
0x18001745c  mov     dword ptr [rbx+28h], 0
0x180017463  mov     qword ptr [rbx+38h], 0
0x18001746b  mov     dword ptr [rbx+48h], 0
0x180017472  mov     qword ptr [rcx+98h], 0
0x18001747d  mov     qword ptr [rcx+0A0h], 0
0x180017488  call    memset_0
0x18001748d  mov     dword ptr [rbx+0F8h], 1
0x180017497  lea     r8, [rdi+30h]; struct wil::CallContextInfo *
0x18001749b  xor     eax, eax
0x18001749d  lea     rcx, [rdi+120h]; this
0x1800174a4  mov     [rbx+100h], rax
0x1800174ab  xor     r9d, r9d; bool
0x1800174ae  mov     [rdi+110h], rbx
0x1800174b5  mov     rdx, rdi; struct wil::details::IFailureCallback *
0x1800174b8  mov     [rdi+118h], rax
0x1800174bf  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x1800174c4  mov     rbx, [rsp+28h+arg_0]
0x1800174c9  mov     rax, rdi
0x1800174cc  add     rsp, 20h
0x1800174d0  pop     rdi
0x1800174d1  retn
```
