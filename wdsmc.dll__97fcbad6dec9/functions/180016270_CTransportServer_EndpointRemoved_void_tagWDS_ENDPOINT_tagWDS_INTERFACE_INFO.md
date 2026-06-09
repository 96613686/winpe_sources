# CTransportServer::_EndpointRemoved(void *,tagWDS_ENDPOINT *,tagWDS_INTERFACE_INFO *)

- ea: `0x180016270`
- end: `0x180016330`
- name: `?_EndpointRemoved@CTransportServer@@SAXPEAXPEAUtagWDS_ENDPOINT@@PEAUtagWDS_INTERFACE_INFO@@@Z`
- size: `192`
- prototype: `static void(void *, struct tagWDS_ENDPOINT *, struct tagWDS_INTERFACE_INFO *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180003c0c`
- `0x180016270`
- `0x180026670`
- `0x180026d3a`
- `0x180026d70`

## string_xrefs

- `0x1800162e7`: `WDSMCTP[0x%x] Endpoint removed by WDS Server on %s, killing session.`

## pseudocode

```c
void __fastcall CTransportServer::_EndpointRemoved(
        volatile __int32 *a1,
        struct tagWDS_ENDPOINT *a2,
        struct tagWDS_INTERFACE_INFO *a3)
{
  size_t v5; // r8
  const unsigned __int16 *v6; // r8
  _QWORD v7[2]; // [rsp+20h] [rbp-C8h] BYREF
  int v8; // [rsp+30h] [rbp-B8h]
  int v9; // [rsp+40h] [rbp-A8h] BYREF
  char v10; // [rsp+44h] [rbp-A4h] BYREF

  if ( g_ErrLibTraceFunction )
  {
    v5 = *((unsigned int *)a3 + 4);
    v7[0] = 0;
    v7[1] = 0;
    v8 = v5;
    memmove_0(v7, a3, v5);
    CIPString::Initialize((CIPString *)&v9, (struct tagWDS_IP_ADDRESS6 *)v7);
    v6 = (const unsigned __int16 *)&v10;
    if ( v9 )
      v6 = L"<<Failed>>";
    g_ErrLibTraceFunction(
      L"WDSMCTP[0x%x] Endpoint removed by WDS Server on %s, killing session.",
      *((unsigned int *)a1 + 554),
      v6);
  }
  _InterlockedExchange(a1 + 564, 1);
  (*(void (__fastcall **)(_QWORD, struct tagWDS_ENDPOINT *))(**((_QWORD **)a1 + 5) + 48LL))(*((_QWORD *)a1 + 5), a2);
}

```

## disassembly

```asm
0x180016270  push    rbx
0x180016272  sub     rsp, 0E0h
0x180016279  mov     rax, cs:__security_cookie
0x180016280  xor     rax, rsp
0x180016283  mov     [rsp+0E8h+var_18], rax
0x18001628b  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180016293  mov     rax, r8
0x180016296  mov     rbx, rcx
0x180016299  jz      short loc_1800162FB
0x18001629b  mov     r8d, [r8+10h]; Size
0x18001629f  xor     ecx, ecx
0x1800162a1  mov     [rsp+0E8h+var_C8], rcx
0x1800162a6  mov     rdx, rax; Src
0x1800162a9  mov     [rsp+0E8h+var_C0], rcx
0x1800162ae  lea     rcx, [rsp+0E8h+var_C8]; void *
0x1800162b3  mov     [rsp+0E8h+var_B8], r8d
0x1800162b8  call    memmove_0
0x1800162bd  lea     rdx, [rsp+0E8h+var_C8]; struct tagWDS_IP_ADDRESS6 *
0x1800162c2  lea     rcx, [rsp+0E8h+var_A8]; this
0x1800162c7  call    ?Initialize@CIPString@@QEAAKPEAUtagWDS_IP_ADDRESS6@@@Z; CIPString::Initialize(tagWDS_IP_ADDRESS6 *)
0x1800162cc  cmp     [rsp+0E8h+var_A8], 0
0x1800162d1  lea     rax, aFailed; "<<Failed>>"
0x1800162d8  mov     edx, [rbx+8A8h]
0x1800162de  lea     r8, [rsp+0E8h+var_A4]
0x1800162e3  cmovnz  r8, rax
0x1800162e7  lea     rcx, aWdsmctp0xXEndp; "WDSMCTP[0x%x] Endpoint removed by WDS S"...
0x1800162ee  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800162f5  call    cs:__guard_dispatch_icall_fptr
0x1800162fb  mov     eax, 1
0x180016300  xchg    eax, [rbx+8D0h]
0x180016306  mov     rcx, [rbx+28h]
0x18001630a  mov     rax, [rcx]
0x18001630d  mov     rax, [rax+30h]
0x180016311  call    cs:__guard_dispatch_icall_fptr
0x180016317  mov     rcx, [rsp+0E8h+var_18]
0x18001631f  xor     rcx, rsp; StackCookie
0x180016322  call    __security_check_cookie
0x180016327  add     rsp, 0E0h
0x18001632e  pop     rbx
0x18001632f  retn
```
