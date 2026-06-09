# CInterfaceHandler::OpenEndpoint(CWdsProvider *,tagWDS_ENDPOINT *,ulong,tagWDS_PROPERTY *,void * *)

- ea: `0x18001385c`
- end: `0x180013936`
- name: `?OpenEndpoint@CInterfaceHandler@@QEAAKPEAVCWdsProvider@@PEAUtagWDS_ENDPOINT@@KPEAUtagWDS_PROPERTY@@PEAPEAX@Z`
- size: `218`
- prototype: `__int64 __fastcall(CInterfaceHandler *this, struct CWdsProvider *, struct tagWDS_ENDPOINT *, unsigned int, struct tagWDS_PROPERTY *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180011700`

## callees

- `0x180002ab0`
- `0x180005354`
- `0x18001385c`
- `0x1800139c4`
- `0x180013af8`

## pseudocode

```c
__int64 __fastcall CInterfaceHandler::OpenEndpoint(
        CInterfaceHandler *this,
        struct CWdsProvider *a2,
        struct tagWDS_ENDPOINT *a3,
        unsigned int a4,
        struct tagWDS_PROPERTY *a5,
        void **a6)
{
  int v6; // r10d
  unsigned int v7; // edi
  unsigned int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  struct CRegEndpoint *v12; // rbx
  __int64 v13; // rax
  const wchar_t *v14; // r9
  struct CRegEndpoint *v16; // [rsp+50h] [rbp+18h] BYREF

  v16 = 0;
  v6 = *((_DWORD *)a3 + 1);
  if ( v6 )
  {
    if ( v6 != 1 )
      return 87;
    v8 = CRpcHandler::OpenEndpoint((CInterfaceHandler *)((char *)this + 66832), a2, a3, a4, a5, &v16);
    v11 = 217;
  }
  else
  {
    v8 = CUdpHandler::OpenEndpoint((CInterfaceHandler *)((char *)this + 1112), a2, a3, a4, a5, &v16);
    v11 = 226;
  }
  v7 = ElValidateWin32_3(v8, v9, v10, v11);
  if ( !v7 )
  {
    v12 = v16;
    if ( (Microsoft_Windows_Deployment_Services_DiagnosticsEnableBits & 1) != 0 )
    {
      v13 = *((_QWORD *)v16 + 8);
      if ( v13 )
        v14 = *(const wchar_t **)(v13 + 16);
      else
        v14 = L"<Unknown>";
      McTemplateU0qzz_EventWriteTransfer(
        (char *)v16 + 1288,
        EndpointOpened,
        *((unsigned int *)v16 + 19),
        v14,
        (char *)v16 + 1288);
    }
    *a6 = v12;
  }
  return v7;
}

```

## disassembly

```asm
0x18001385c  mov     [rsp+arg_0], rbx
0x180013861  push    rdi
0x180013862  sub     rsp, 30h
0x180013866  and     [rsp+38h+arg_10], 0
0x18001386c  mov     r10d, [r8+4]
0x180013870  test    r10d, r10d
0x180013873  jz      short loc_1800138AD
0x180013875  cmp     r10d, 1
0x180013879  jz      short loc_180013885
0x18001387b  mov     edi, 57h ; 'W'
0x180013880  jmp     loc_180013928
0x180013885  lea     rax, [rsp+38h+arg_10]
0x18001388a  add     rcx, 10510h; this
0x180013891  mov     [rsp+38h+var_10], rax; struct CRegEndpoint **
0x180013896  mov     rax, [rsp+38h+arg_20]
0x18001389b  mov     [rsp+38h+var_18], rax; struct tagWDS_PROPERTY *
0x1800138a0  call    ?OpenEndpoint@CRpcHandler@@QEAAKPEAVCWdsProvider@@PEAUtagWDS_ENDPOINT@@KPEAUtagWDS_PROPERTY@@PEAPEAVCRegEndpoint@@@Z; CRpcHandler::OpenEndpoint(CWdsProvider *,tagWDS_ENDPOINT *,ulong,tagWDS_PROPERTY *,CRegEndpoint * *)
0x1800138a5  mov     r9d, 0D9h; unsigned int
0x1800138ab  jmp     short loc_1800138D3
0x1800138ad  lea     rax, [rsp+38h+arg_10]
0x1800138b2  add     rcx, 458h; this
0x1800138b9  mov     [rsp+38h+var_10], rax; struct CRegEndpoint **
0x1800138be  mov     rax, [rsp+38h+arg_20]
0x1800138c3  mov     [rsp+38h+var_18], rax; struct tagWDS_PROPERTY *
0x1800138c8  call    ?OpenEndpoint@CUdpHandler@@QEAAKPEAVCWdsProvider@@PEAUtagWDS_ENDPOINT@@KPEAUtagWDS_PROPERTY@@PEAPEAVCRegEndpoint@@@Z; CUdpHandler::OpenEndpoint(CWdsProvider *,tagWDS_ENDPOINT *,ulong,tagWDS_PROPERTY *,CRegEndpoint * *)
0x1800138cd  mov     r9d, 0E2h
0x1800138d3  mov     ecx, eax
0x1800138d5  call    ElValidateWin32_3
0x1800138da  mov     edi, eax
0x1800138dc  test    eax, eax
0x1800138de  jnz     short loc_180013928
0x1800138e0  test    cs:Microsoft_Windows_Deployment_Services_DiagnosticsEnableBits, 1
0x1800138e7  mov     rbx, [rsp+38h+arg_10]
0x1800138ec  jz      short loc_180013920
0x1800138ee  mov     rax, [rbx+40h]
0x1800138f2  lea     rcx, [rbx+508h]
0x1800138f9  test    rax, rax
0x1800138fc  jz      short loc_180013904
0x1800138fe  mov     r9, [rax+10h]
0x180013902  jmp     short loc_18001390B
0x180013904  lea     r9, aUnknown_0; "<Unknown>"
0x18001390b  mov     r8d, [rbx+4Ch]
0x18001390f  lea     rdx, EndpointOpened
0x180013916  mov     [rsp+38h+var_18], rcx
0x18001391b  call    McTemplateU0qzz_EventWriteTransfer
0x180013920  mov     rax, [rsp+38h+arg_28]
0x180013925  mov     [rax], rbx
0x180013928  mov     rbx, [rsp+38h+arg_0]
0x18001392d  mov     eax, edi
0x18001392f  add     rsp, 30h
0x180013933  pop     rdi
0x180013934  retn
```
