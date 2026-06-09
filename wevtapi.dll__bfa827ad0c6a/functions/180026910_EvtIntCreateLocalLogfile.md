# EvtIntCreateLocalLogfile

- ea: `0x180026910`
- end: `0x180026a22`
- name: `EvtIntCreateLocalLogfile`
- size: `274`
- prototype: `void *__fastcall(wchar_t *, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x180006870`
- `0x180007010`
- `0x180008924`
- `0x18000a020`
- `0x18001a71c`
- `0x180023548`
- `0x1800265dc`
- `0x180026910`
- `0x180038fa4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800269f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800269f7`

## pseudocode

```c
void *__fastcall EvtIntCreateLocalLogfile(wchar_t *a1, int a2)
{
  LocalEvtxFileObject *v3; // rax
  ObjectTable *v4; // rcx
  volatile signed __int32 *v5; // rbx
  DWORD v6; // edi
  void *v7; // rbx
  EvtException *v9; // [rsp+20h] [rbp-38h] BYREF
  __int128 pExceptionObject; // [rsp+28h] [rbp-30h] BYREF
  __int64 v11; // [rsp+38h] [rbp-20h]
  int v12; // [rsp+40h] [rbp-18h]
  int v13; // [rsp+44h] [rbp-14h]
  int v14; // [rsp+48h] [rbp-10h]
  __int64 v15; // [rsp+70h] [rbp+18h] BYREF
  LocalEvtxFileObject *v16; // [rsp+78h] [rbp+20h]

  try
  {
    v15 = 0;
    if ( a2 || !a1 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids, 87);
      }
      pExceptionObject = 0;
      v11 = 0;
      v12 = 87;
      v13 = -1;
      v14 = 270;
      throw (EvtException *)&pExceptionObject;
    }
    v3 = (LocalEvtxFileObject *)operator new(0x368u);
    v16 = v3;
    if ( v3 )
      v5 = (volatile signed __int32 *)LocalEvtxFileObject::LocalEvtxFileObject(v3, a1);
    else
      v5 = 0;
    if ( v5 )
      _InterlockedIncrement(v5 + 2);
    v6 = ObjectTable::AddObject(v4, (struct Object *)v5, (struct EvtHandleRef *)&v15);
    if ( v5 )
      wmi::RefBase::Release((wmi::RefBase *)v5);
  }
  catch ( EvtException *v9 )
  {
    v6 = *((_DWORD *)v9 + 6);
  }
  v15 = 0;
  if ( a2 || !a1 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids, 87);
    }
    pExceptionObject = 0;
    v11 = 0;
    v12 = 87;
    v13 = -1;
    v14 = 270;
    throw (EvtException *)&pExceptionObject;
  }
  v3 = (LocalEvtxFileObject *)operator new(0x368u);
  v16 = v3;
}

```

## disassembly

```asm
0x180026910  mov     [rsp+arg_0], rbx
0x180026915  push    rdi
0x180026916  sub     rsp, 50h
0x18002691a  mov     rbx, rcx
0x18002691d  mov     [rsp+58h+arg_10], 0
0x180026926  test    edx, edx
0x180026928  jnz     short loc_18002697D
0x18002692a  test    rcx, rcx
0x18002692d  jz      short loc_18002697D
0x18002692f  mov     ecx, 368h; dwBytes
0x180026934  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026939  mov     [rsp+58h+arg_18], rax
0x18002693e  test    rax, rax
0x180026941  jz      short loc_180026953
0x180026943  mov     rdx, rbx; wchar_t *
0x180026946  mov     rcx, rax; this
0x180026949  call    ??0LocalEvtxFileObject@@QEAA@PEB_W@Z; LocalEvtxFileObject::LocalEvtxFileObject(wchar_t const *)
0x18002694e  mov     rbx, rax
0x180026951  jmp     short loc_180026955
0x180026953  xor     ebx, ebx
0x180026955  test    rbx, rbx
0x180026958  jz      short loc_18002695E
0x18002695a  lock inc dword ptr [rbx+8]
0x18002695e  lea     r8, [rsp+58h+arg_10]; struct EvtHandleRef *
0x180026963  mov     rdx, rbx; struct Object *
0x180026966  call    ?AddObject@ObjectTable@@QEAAKPEAVObject@@AEAVEvtHandleRef@@@Z; ObjectTable::AddObject(Object *,EvtHandleRef &)
0x18002696b  mov     edi, eax
0x18002696d  test    rbx, rbx
0x180026970  jz      short loc_18002697B
0x180026972  mov     rcx, rbx; this
0x180026975  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x18002697a  nop
0x18002697b  jmp     short loc_1800269F5
0x18002697d  lea     rax, WPP_GLOBAL_Control
0x180026984  mov     rcx, cs:WPP_GLOBAL_Control
0x18002698b  cmp     rcx, rax
0x18002698e  jz      short loc_1800269B5
0x180026990  test    byte ptr [rcx+1Ch], 1
0x180026994  jz      short loc_1800269B5
0x180026996  cmp     byte ptr [rcx+19h], 2
0x18002699a  jb      short loc_1800269B5
0x18002699c  mov     edx, 0Ch
0x1800269a1  lea     r9d, [rdx+4Bh]
0x1800269a5  lea     r8, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids
0x1800269ac  mov     rcx, [rcx+10h]
0x1800269b0  call    WPP_SF_D
0x1800269b5  xorps   xmm0, xmm0
0x1800269b8  movdqu  [rsp+58h+pExceptionObject], xmm0
0x1800269be  mov     [rsp+58h+var_20], 0
0x1800269c7  mov     [rsp+58h+var_18], 57h ; 'W'
0x1800269cf  mov     [rsp+58h+var_14], 0FFFFFFFFh
0x1800269d7  mov     [rsp+58h+var_10], 10Eh
0x1800269df  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800269e6  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x1800269eb  call    _CxxThrowException_0
0x1800269f1  mov     edi, [rsp+58h+arg_8]
0x1800269f5  mov     ecx, edi; dwErrCode
0x1800269f7  call    cs:__imp_SetLastError
0x1800269fd  lea     rcx, [rsp+58h+arg_10]; this
0x180026a02  call    ?Detach@EvtHandleRef@@QEAAPEAXXZ; EvtHandleRef::Detach(void)
0x180026a07  mov     rbx, rax
0x180026a0a  lea     rcx, [rsp+58h+arg_10]; this
0x180026a0f  call    ??1EvtHandleRef@@QEAA@XZ; EvtHandleRef::~EvtHandleRef(void)
0x180026a14  mov     rax, rbx
0x180026a17  mov     rbx, [rsp+58h+arg_0]
0x180026a1c  add     rsp, 50h
0x180026a20  pop     rdi
0x180026a21  retn
```
