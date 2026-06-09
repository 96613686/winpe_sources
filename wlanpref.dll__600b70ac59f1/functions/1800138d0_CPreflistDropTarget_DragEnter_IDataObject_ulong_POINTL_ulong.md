# CPreflistDropTarget::DragEnter(IDataObject *,ulong,_POINTL,ulong *)

- ea: `0x1800138d0`
- end: `0x180013992`
- name: `?DragEnter@CPreflistDropTarget@@UEAAJPEAUIDataObject@@KU_POINTL@@PEAK@Z`
- size: `194`
- prototype: `__int64 __fastcall(const ITEMIDLIST **this, struct IDataObject *, __int64, struct _POINTL, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003458`
- `0x180013738`
- `0x1800138d0`
- `0x18002749c`
- `0x180027594`
- `0x180030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPreflistDropTarget::DragEnter(
        const ITEMIDLIST **this,
        struct IDataObject *a2,
        __int64 a3,
        struct _POINTL a4,
        unsigned int *a5)
{
  int v6; // ebx
  _BYTE v8[104]; // [rsp+20h] [rbp-68h] BYREF
  struct IDataObject *v9; // [rsp+90h] [rbp+8h] BYREF

  if ( *((_BYTE *)this + 161) )
  {
    *a5 = 0;
  }
  else
  {
    v9 = a2;
    if ( a2 )
      ((void (__fastcall *)(struct IDataObject *))a2->lpVtbl->AddRef)(a2);
    CProfile::CProfile((CProfile *)v8);
    v6 = DataObjectToProfile(&v9, this[8], (CProfile *)v8);
    if ( v6 < 0 )
    {
      CProfile::~CProfile((CProfile *)v8);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v9);
      return (unsigned int)v6;
    }
    *a5 = v8[81] == 0 ? 2 : 0;
    CProfile::~CProfile((CProfile *)v8);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v9);
  }
  return 0;
}

```

## disassembly

```asm
0x1800138d0  push    rbx
0x1800138d2  sub     rsp, 80h
0x1800138d9  mov     rbx, rcx
0x1800138dc  cmp     byte ptr [rcx+0A1h], 0
0x1800138e3  jz      short loc_1800138F8
0x1800138e5  mov     rax, [rsp+88h+arg_20]
0x1800138ed  mov     dword ptr [rax], 0
0x1800138f3  jmp     loc_180013987
0x1800138f8  mov     [rsp+88h+arg_0], rdx
0x180013900  test    rdx, rdx
0x180013903  jz      short loc_180013915
0x180013905  mov     rax, [rdx]
0x180013908  mov     rcx, rdx
0x18001390b  mov     rax, [rax+8]
0x18001390f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013914  nop
0x180013915  lea     rcx, [rsp+88h+var_68]; this
0x18001391a  call    ??0CProfile@@QEAA@XZ; CProfile::CProfile(void)
0x18001391f  nop
0x180013920  lea     r8, [rsp+88h+var_68]
0x180013925  mov     rdx, [rbx+40h]
0x180013929  lea     rcx, [rsp+88h+arg_0]
0x180013931  call    ?DataObjectToProfile@@YAJAEAV?$CComPtr@UIDataObject@@@ATL@@PEFBU_ITEMIDLIST@@AEAVCProfile@@@Z; DataObjectToProfile(ATL::CComPtr<IDataObject> &,_ITEMIDLIST const *,CProfile &)
0x180013936  mov     ebx, eax
0x180013938  test    eax, eax
0x18001393a  jns     short loc_180013958
0x18001393c  lea     rcx, [rsp+88h+var_68]; this
0x180013941  call    ??1CProfile@@UEAA@XZ; CProfile::~CProfile(void)
0x180013946  nop
0x180013947  lea     rcx, [rsp+88h+arg_0]
0x18001394f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180013954  mov     eax, ebx
0x180013956  jmp     short loc_180013989
0x180013958  mov     al, [rsp+88h+var_17]
0x18001395c  neg     al
0x18001395e  sbb     ecx, ecx
0x180013960  not     ecx
0x180013962  and     ecx, 2
0x180013965  mov     rax, [rsp+88h+arg_20]
0x18001396d  mov     [rax], ecx
0x18001396f  lea     rcx, [rsp+88h+var_68]; this
0x180013974  call    ??1CProfile@@UEAA@XZ; CProfile::~CProfile(void)
0x180013979  nop
0x18001397a  lea     rcx, [rsp+88h+arg_0]
0x180013982  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180013987  xor     eax, eax
0x180013989  add     rsp, 80h
0x180013990  pop     rbx
0x180013991  retn
```
