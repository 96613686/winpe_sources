# CStorageItemsDataFormat::CreateFileContents(tagFORMATETC const *,tagSTGMEDIUM *)

- ea: `0x180023138`
- end: `0x180023366`
- name: `?CreateFileContents@CStorageItemsDataFormat@@QEAAJPEBUtagFORMATETC@@PEAUtagSTGMEDIUM@@@Z`
- size: `558`
- prototype: `__int64 __fastcall(CStorageItemsDataFormat *__hidden this, const struct tagFORMATETC *, struct tagSTGMEDIUM *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180018bb4`

## callees

- `0x18000d568`
- `0x180023138`
- `0x180081010`

## import_xrefs

- `SHCORE!CreateStreamOverRandomAccessStream` at `0x18002328b`
- `SHCORE!CreateStreamOverRandomAccessStream` at `0x18002328b`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180023307`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180023307`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800232f5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800232f5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CStorageItemsDataFormat::CreateFileContents(
        CStorageItemsDataFormat *this,
        const struct tagFORMATETC *a2,
        struct tagSTGMEDIUM *a3)
{
  int StreamOverRandomAccessStream; // ebx
  DWORD dwAspect; // ecx
  __int64 v8; // rcx
  __int64 lindex; // rdx
  __int64 v10; // rdi
  __int64 v11; // rcx
  __int64 v12; // rcx
  unsigned int StringW; // eax
  __int64 v14; // rcx
  __int64 (__fastcall ***v15)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v17; // [rsp+20h] [rbp-20h] BYREF
  __int64 v18; // [rsp+28h] [rbp-18h] BYREF
  __int64 (__fastcall ***v19)(_QWORD, GUID *, __int64 *); // [rsp+30h] [rbp-10h] BYREF
  unsigned int v20; // [rsp+68h] [rbp+28h] BYREF
  __int64 Buffer; // [rsp+78h] [rbp+38h] BYREF

  *(_OWORD *)&a3->tymed = 0;
  a3->pUnkForRelease = 0;
  if ( (a2->tymed & 4) != 0 )
  {
    dwAspect = a2->dwAspect;
    if ( ((dwAspect - 1) & 0xFFFFFFFC) != 0 || dwAspect == 2 )
    {
      return (unsigned int)-2147221397;
    }
    else
    {
      v8 = *((_QWORD *)this + 3);
      if ( v8 )
      {
        v20 = 0;
        StreamOverRandomAccessStream = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v8 + 56LL))(
                                         v8,
                                         &v20);
        if ( StreamOverRandomAccessStream >= 0 )
        {
          lindex = (unsigned int)a2->lindex;
          if ( (unsigned int)lindex < v20 )
          {
            v19 = 0;
            StreamOverRandomAccessStream = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 3)
                                                                                              + 48LL))(
                                             *((_QWORD *)this + 3),
                                             lindex,
                                             &v19);
            if ( StreamOverRandomAccessStream >= 0 )
            {
              v18 = 0;
              StreamOverRandomAccessStream = (**v19)(v19, &GUID_fa3f6186_4214_428c_a64c_14c9ac7315ea, &v18);
              if ( StreamOverRandomAccessStream < 0 )
              {
                Buffer = 0;
                StringW = LoadStringW(&_ImageBase, 0x20u, (LPWSTR)&Buffer, 0);
                if ( StringW )
                  RoOriginateErrorW((unsigned int)StreamOverRandomAccessStream, StringW, Buffer);
              }
              else
              {
                v17 = 0;
                StreamOverRandomAccessStream = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v18 + 64LL))(
                                                 v18,
                                                 0,
                                                 &v17);
                if ( StreamOverRandomAccessStream >= 0 )
                {
                  Buffer = 0;
                  v10 = v17;
                  StreamOverRandomAccessStream = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>>(v17);
                  if ( StreamOverRandomAccessStream >= 0 )
                  {
                    StreamOverRandomAccessStream = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v10 + 64LL))(
                                                     v10,
                                                     &Buffer);
                    if ( StreamOverRandomAccessStream >= 0 )
                    {
                      StreamOverRandomAccessStream = CreateStreamOverRandomAccessStream(
                                                       Buffer,
                                                       &GUID_0000000c_0000_0000_c000_000000000046,
                                                       &a3->hBitmap);
                      if ( StreamOverRandomAccessStream >= 0 )
                        a3->tymed = 4;
                    }
                  }
                  v11 = Buffer;
                  if ( Buffer )
                  {
                    Buffer = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
                  }
                }
                v12 = v17;
                if ( v17 )
                {
                  v17 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
                }
              }
              v14 = v18;
              if ( v18 )
              {
                v18 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
              }
            }
            v15 = v19;
            if ( v19 )
            {
              v19 = 0;
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v15)[2])(v15);
            }
          }
          else
          {
            return (unsigned int)-2147221400;
          }
        }
      }
      else
      {
        return (unsigned int)-2147418113;
      }
    }
  }
  else
  {
    return (unsigned int)-2147221404;
  }
  return (unsigned int)StreamOverRandomAccessStream;
}

```

## disassembly

```asm
0x180023138  mov     [rsp-18h+arg_0], rbx
0x18002313d  mov     [rsp-18h+arg_10], rsi
0x180023142  push    rbp
0x180023143  push    rdi
0x180023144  push    r14
0x180023146  mov     rbp, rsp
0x180023149  sub     rsp, 40h
0x18002314d  mov     rsi, r8
0x180023150  mov     rdi, rdx
0x180023153  mov     r14, rcx
0x180023156  xorps   xmm0, xmm0
0x180023159  xor     eax, eax
0x18002315b  movups  xmmword ptr [r8], xmm0
0x18002315f  mov     [r8+10h], rax
0x180023163  test    byte ptr [rdx+18h], 4
0x180023167  jnz     short loc_180023173
0x180023169  mov     ebx, 80040064h
0x18002316e  jmp     loc_180023351
0x180023173  mov     ecx, [rdx+10h]
0x180023176  lea     eax, [rcx-1]
0x180023179  test    eax, 0FFFFFFFCh
0x18002317e  jnz     loc_18002334C
0x180023184  cmp     ecx, 2
0x180023187  jz      loc_18002334C
0x18002318d  mov     rcx, [r14+18h]
0x180023191  test    rcx, rcx
0x180023194  jnz     short loc_1800231A0
0x180023196  mov     ebx, 8000FFFFh
0x18002319b  jmp     loc_180023351
0x1800231a0  mov     [rbp+arg_8], 0
0x1800231a7  mov     rax, [rcx]
0x1800231aa  lea     rdx, [rbp+arg_8]
0x1800231ae  mov     rax, [rax+38h]
0x1800231b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800231b7  mov     ebx, eax
0x1800231b9  test    eax, eax
0x1800231bb  js      loc_180023351
0x1800231c1  mov     edx, [rdi+14h]
0x1800231c4  cmp     edx, [rbp+arg_8]
0x1800231c7  jb      short loc_1800231D3
0x1800231c9  mov     ebx, 80040068h
0x1800231ce  jmp     loc_180023351
0x1800231d3  mov     [rbp+var_10], 0
0x1800231db  mov     rcx, [r14+18h]
0x1800231df  mov     rax, [rcx]
0x1800231e2  lea     r8, [rbp+var_10]
0x1800231e6  mov     rax, [rax+30h]
0x1800231ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800231ef  mov     ebx, eax
0x1800231f1  test    eax, eax
0x1800231f3  js      loc_18002332C
0x1800231f9  mov     [rbp+var_18], 0
0x180023201  mov     rcx, [rbp+var_10]
0x180023205  mov     rax, [rcx]
0x180023208  lea     r8, [rbp+var_18]
0x18002320c  lea     rdx, _GUID_fa3f6186_4214_428c_a64c_14c9ac7315ea
0x180023213  mov     rax, [rax]
0x180023216  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002321b  mov     ebx, eax
0x18002321d  test    eax, eax
0x18002321f  js      loc_1800232DB
0x180023225  mov     [rbp+var_20], 0
0x18002322d  mov     rcx, [rbp+var_18]
0x180023231  mov     rax, [rcx]
0x180023234  lea     r8, [rbp+var_20]
0x180023238  xor     edx, edx
0x18002323a  mov     rax, [rax+40h]
0x18002323e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023243  mov     ebx, eax
0x180023245  test    eax, eax
0x180023247  js      short loc_1800232BB
0x180023249  mov     [rbp+Buffer], 0
0x180023251  mov     rdi, [rbp+var_20]
0x180023255  mov     rcx, rdi
0x180023258  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUIRandomAccessStream@Streams@Storage@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> *,tagCOWAIT_FLAGS,void *)
0x18002325d  mov     ebx, eax
0x18002325f  test    eax, eax
0x180023261  js      short loc_18002329D
0x180023263  mov     rax, [rdi]
0x180023266  lea     rdx, [rbp+Buffer]
0x18002326a  mov     rcx, rdi
0x18002326d  mov     rax, [rax+40h]
0x180023271  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023276  mov     ebx, eax
0x180023278  test    eax, eax
0x18002327a  js      short loc_18002329D
0x18002327c  lea     r8, [rsi+8]
0x180023280  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x180023287  mov     rcx, [rbp+Buffer]
0x18002328b  call    cs:__imp_CreateStreamOverRandomAccessStream
0x180023291  mov     ebx, eax
0x180023293  test    eax, eax
0x180023295  js      short loc_18002329D
0x180023297  mov     dword ptr [rsi], 4
0x18002329d  mov     rcx, [rbp+Buffer]
0x1800232a1  test    rcx, rcx
0x1800232a4  jz      short loc_1800232BB
0x1800232a6  mov     [rbp+Buffer], 0
0x1800232ae  mov     rax, [rcx]
0x1800232b1  mov     rax, [rax+10h]
0x1800232b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800232ba  nop
0x1800232bb  mov     rcx, [rbp+var_20]
0x1800232bf  test    rcx, rcx
0x1800232c2  jz      short loc_1800232D9
0x1800232c4  mov     [rbp+var_20], 0
0x1800232cc  mov     rax, [rcx]
0x1800232cf  mov     rax, [rax+10h]
0x1800232d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800232d8  nop
0x1800232d9  jmp     short loc_18002330E
0x1800232db  mov     [rbp+Buffer], 0
0x1800232e3  xor     r9d, r9d; cchBufferMax
0x1800232e6  lea     r8, [rbp+Buffer]; lpBuffer
0x1800232ea  lea     edx, [r9+20h]; uID
0x1800232ee  lea     rcx, __ImageBase; hInstance
0x1800232f5  call    cs:__imp_LoadStringW
0x1800232fb  test    eax, eax
0x1800232fd  jz      short loc_18002330E
0x1800232ff  mov     r8, [rbp+Buffer]
0x180023303  mov     edx, eax
0x180023305  mov     ecx, ebx
0x180023307  call    cs:__imp_RoOriginateErrorW
0x18002330d  nop
0x18002330e  mov     rcx, [rbp+var_18]
0x180023312  test    rcx, rcx
0x180023315  jz      short loc_18002332C
0x180023317  mov     [rbp+var_18], 0
0x18002331f  mov     rax, [rcx]
0x180023322  mov     rax, [rax+10h]
0x180023326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002332b  nop
0x18002332c  mov     rcx, [rbp+var_10]
0x180023330  test    rcx, rcx
0x180023333  jz      short loc_18002334A
0x180023335  mov     [rbp+var_10], 0
0x18002333d  mov     rax, [rcx]
0x180023340  mov     rax, [rax+10h]
0x180023344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023349  nop
0x18002334a  jmp     short loc_180023351
0x18002334c  mov     ebx, 8004006Bh
0x180023351  mov     eax, ebx
0x180023353  mov     rbx, [rsp+40h+arg_0]
0x180023358  mov     rsi, [rsp+40h+arg_10]
0x18002335d  add     rsp, 40h
0x180023361  pop     r14
0x180023363  pop     rdi
0x180023364  pop     rbp
0x180023365  retn
```
