# CLowResourceVideoPlayer::_ThreadProc(void)

- ea: `0x180062cd0`
- end: `0x180062f9b`
- name: `?_ThreadProc@CLowResourceVideoPlayer@@AEAAJXZ`
- size: `715`
- prototype: `__int64 __fastcall(CLowResourceVideoPlayer *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180063070`

## callees

- `0x180062bb0`
- `0x180062cd0`
- `0x18006309c`
- `0x180063360`
- `0x18006342c`
- `0x180078010`

## import_xrefs

- `msvcrt!rand` at `0x180062f1e`
- `msvcrt!rand` at `0x180062f1e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180062eb5`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180062f3e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180062eb5`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180062f3e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180062e8e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180062e8e`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x180062d28`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x180062d28`
- `MFPlat!MFShutdown` at `0x180062f6b`
- `MFPlat!MFShutdown` at `0x180062f6b`
- `MFPlat!MFStartup` at `0x180062cef`
- `MFPlat!MFStartup` at `0x180062cef`

## pseudocode

```c
__int64 __fastcall CLowResourceVideoPlayer::_ThreadProc(CLowResourceVideoPlayer *this)
{
  HRESULT VideoSourceReaderFromStream; // ebx
  const WCHAR *v3; // rcx
  const struct _GUID *v4; // rdx
  IStream *v5; // rcx
  struct IMFSourceReader *v6; // rsi
  struct IMFMediaType **v7; // r9
  char v8; // si
  __int64 v9; // r14
  ULONGLONG v10; // r15
  ULONGLONG TickCount64; // rax
  __int64 v12; // rcx
  unsigned int v13; // eax
  struct IMFSample *v14; // rcx
  struct IMFSourceReader *v15; // rcx
  struct IMFSample *v17; // [rsp+40h] [rbp-30h] BYREF
  __int64 v18; // [rsp+48h] [rbp-28h] BYREF
  __int64 v19; // [rsp+50h] [rbp-20h] BYREF
  __int128 v20; // [rsp+58h] [rbp-18h] BYREF
  __int64 v21; // [rsp+68h] [rbp-8h]
  IStream *ppstm; // [rsp+B8h] [rbp+48h] BYREF
  int v23; // [rsp+C0h] [rbp+50h] BYREF
  struct IMFSourceReader *v24; // [rsp+C8h] [rbp+58h] BYREF

  VideoSourceReaderFromStream = MFStartup(0x20070u, 1u);
  if ( VideoSourceReaderFromStream >= 0 )
  {
    v3 = (const WCHAR *)*((_QWORD *)this + 6);
    v24 = 0;
    ppstm = 0;
    VideoSourceReaderFromStream = SHCreateStreamOnFileEx(v3, 0x20u, 0x80u, 0, 0, &ppstm);
    if ( VideoSourceReaderFromStream >= 0 )
      VideoSourceReaderFromStream = CreateVideoSourceReaderFromStream(ppstm, v4, (void **)&v24);
    v5 = ppstm;
    if ( ppstm )
    {
      ppstm = 0;
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)v5 + 16LL))(v5);
    }
    if ( VideoSourceReaderFromStream >= 0 )
    {
      v6 = v24;
      VideoSourceReaderFromStream = ((__int64 (__fastcall *)(struct IMFSourceReader *, __int64, _QWORD))v24->lpVtbl->SetStreamSelection)(
                                      v24,
                                      4294967294LL,
                                      0);
      if ( VideoSourceReaderFromStream >= 0 )
      {
        VideoSourceReaderFromStream = ((__int64 (__fastcall *)(struct IMFSourceReader *, __int64, __int64))v6->lpVtbl->SetStreamSelection)(
                                        v6,
                                        4294967292LL,
                                        1);
        if ( VideoSourceReaderFromStream >= 0 )
        {
          VideoSourceReaderFromStream = DetermineFrameDimensions(v24, (int *)this + 15, (int *)this + 16, v7);
          if ( VideoSourceReaderFromStream >= 0 )
          {
            v8 = 1;
            v9 = 0;
            v10 = 0;
            VideoSourceReaderFromStream = SetTargetMediaType(v24);
            while ( VideoSourceReaderFromStream >= 0 )
            {
              if ( !*((_BYTE *)this + 24) )
                break;
              v23 = 0;
              LODWORD(ppstm) = 0;
              v19 = 0;
              v17 = 0;
              VideoSourceReaderFromStream = ((__int64 (__fastcall *)(struct IMFSourceReader *, __int64, _QWORD, int *, IStream **, __int64 *, struct IMFSample **))v24->lpVtbl->ReadSample)(
                                              v24,
                                              4294967292LL,
                                              0,
                                              &v23,
                                              &ppstm,
                                              &v19,
                                              &v17);
              if ( VideoSourceReaderFromStream >= 0 )
              {
                if ( ((unsigned __int8)ppstm & 2) != 0 )
                {
                  if ( !*((_BYTE *)this + 56) || v8 )
                  {
                    *((_BYTE *)this + 24) = 0;
                  }
                  else if ( *((_BYTE *)this + 24) )
                  {
                    v21 = 0;
                    v20 = 0;
                    LOWORD(v20) = 20;
                    VideoSourceReaderFromStream = ((__int64 (__fastcall *)(struct IMFSourceReader *, GUID *, __int128 *))v24->lpVtbl->SetCurrentPosition)(
                                                    v24,
                                                    &GUID_00000000_0000_0000_0000_000000000000,
                                                    &v20);
                    if ( VideoSourceReaderFromStream >= 0 )
                    {
                      v8 = 1;
                      v13 = rand();
                      Sleep(v13 % 0x2711 + 5000);
                    }
                  }
                }
                else
                {
                  v18 = 0;
                  VideoSourceReaderFromStream = ((__int64 (__fastcall *)(struct IMFSample *, __int64 *))v17->lpVtbl->GetSampleTime)(
                                                  v17,
                                                  &v18);
                  if ( VideoSourceReaderFromStream >= 0 )
                  {
                    v18 /= 10000;
                    TickCount64 = GetTickCount64();
                    if ( v8 )
                    {
                      v10 = TickCount64;
                      v9 = v18;
                    }
                    v8 = 0;
                    v12 = v10 + v18 - TickCount64 - v9;
                    if ( v12 >= 0 )
                    {
                      Sleep(v12);
                      if ( *((_BYTE *)this + 24) )
                        CLowResourceVideoPlayer::_PresentSample(this, v17);
                    }
                  }
                }
              }
              v14 = v17;
              if ( v17 )
              {
                v17 = 0;
                ((void (__fastcall *)(struct IMFSample *))v14->lpVtbl->Release)(v14);
              }
            }
          }
        }
      }
    }
    MFShutdown();
    v15 = v24;
    if ( v24 )
    {
      v24 = 0;
      ((void (__fastcall *)(struct IMFSourceReader *))v15->lpVtbl->Release)(v15);
    }
  }
  return (unsigned int)VideoSourceReaderFromStream;
}

```

## disassembly

```asm
0x180062cd0  push    rbp
0x180062cd2  push    rbx
0x180062cd3  push    rsi
0x180062cd4  push    rdi
0x180062cd5  push    r12
0x180062cd7  push    r14
0x180062cd9  push    r15
0x180062cdb  mov     rbp, rsp
0x180062cde  sub     rsp, 70h
0x180062ce2  mov     rdi, rcx
0x180062ce5  mov     edx, 1; dwFlags
0x180062cea  mov     ecx, 20070h; Version
0x180062cef  call    cs:__imp_MFStartup
0x180062cf5  xor     r12d, r12d
0x180062cf8  mov     ebx, eax
0x180062cfa  test    eax, eax
0x180062cfc  js      loc_180062F8A
0x180062d02  mov     rcx, [rdi+30h]; pszFile
0x180062d06  lea     rax, [rbp+arg_8]
0x180062d0a  lea     edx, [r12+20h]; grfMode
0x180062d0f  mov     [rsp+70h+ppstm], rax; ppstm
0x180062d14  lea     r8d, [rdx+60h]; dwAttributes
0x180062d18  mov     [rsp+70h+pstmTemplate], r12; pstmTemplate
0x180062d1d  xor     r9d, r9d; fCreate
0x180062d20  mov     [rbp+arg_18], r12
0x180062d24  mov     [rbp+arg_8], r12
0x180062d28  call    cs:__imp_SHCreateStreamOnFileEx
0x180062d2e  mov     ebx, eax
0x180062d30  test    eax, eax
0x180062d32  js      short loc_180062D43
0x180062d34  mov     rcx, [rbp+arg_8]; struct IStream *
0x180062d38  lea     r8, [rbp+arg_18]; void **
0x180062d3c  call    ?CreateVideoSourceReaderFromStream@@YAJPEAUIStream@@AEBU_GUID@@PEAPEAX@Z; CreateVideoSourceReaderFromStream(IStream *,_GUID const &,void * *)
0x180062d41  mov     ebx, eax
0x180062d43  mov     rcx, [rbp+arg_8]
0x180062d47  test    rcx, rcx
0x180062d4a  jz      short loc_180062D5C
0x180062d4c  mov     [rbp+arg_8], r12
0x180062d50  mov     rax, [rcx]
0x180062d53  mov     rax, [rax+10h]
0x180062d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062d5c  test    ebx, ebx
0x180062d5e  js      loc_180062F6B
0x180062d64  mov     rsi, [rbp+arg_18]
0x180062d68  xor     r8d, r8d
0x180062d6b  mov     edx, 0FFFFFFFEh
0x180062d70  mov     rcx, rsi
0x180062d73  mov     rax, [rsi]
0x180062d76  mov     rax, [rax+20h]
0x180062d7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062d7f  mov     ebx, eax
0x180062d81  test    eax, eax
0x180062d83  js      loc_180062F6B
0x180062d89  mov     rax, [rsi]
0x180062d8c  mov     edx, 0FFFFFFFCh
0x180062d91  mov     r8d, 1
0x180062d97  mov     rcx, rsi
0x180062d9a  mov     rax, [rax+20h]
0x180062d9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062da3  mov     ebx, eax
0x180062da5  test    eax, eax
0x180062da7  js      loc_180062F6B
0x180062dad  mov     rcx, [rbp+arg_18]; struct IMFSourceReader *
0x180062db1  lea     r8, [rdi+40h]; int *
0x180062db5  lea     rdx, [rdi+3Ch]; int *
0x180062db9  call    ?DetermineFrameDimensions@@YAJPEAUIMFSourceReader@@PEAJ1PEAPEAUIMFMediaType@@@Z; DetermineFrameDimensions(IMFSourceReader *,long *,long *,IMFMediaType * *)
0x180062dbe  mov     ebx, eax
0x180062dc0  test    eax, eax
0x180062dc2  js      loc_180062F6B
0x180062dc8  mov     rcx, [rbp+arg_18]; struct IMFSourceReader *
0x180062dcc  mov     sil, 1
0x180062dcf  mov     r14, r12
0x180062dd2  mov     r15, r12
0x180062dd5  call    ?SetTargetMediaType@@YAJPEAUIMFSourceReader@@@Z; SetTargetMediaType(IMFSourceReader *)
0x180062dda  mov     ebx, eax
0x180062ddc  test    eax, eax
0x180062dde  js      loc_180062F6B
0x180062de4  cmp     [rdi+18h], r12b
0x180062de8  jz      loc_180062F6B
0x180062dee  mov     rcx, [rbp+arg_18]
0x180062df2  lea     rdx, [rbp+var_30]
0x180062df6  mov     [rsp+70h+var_40], rdx
0x180062dfb  lea     r9, [rbp+arg_10]
0x180062dff  mov     [rbp+arg_10], r12d
0x180062e03  lea     rdx, [rbp+var_20]
0x180062e07  mov     [rsp+70h+ppstm], rdx
0x180062e0c  xor     r8d, r8d
0x180062e0f  lea     rdx, [rbp+arg_8]
0x180062e13  mov     dword ptr [rbp+arg_8], r12d
0x180062e17  mov     [rbp+var_20], r12
0x180062e1b  mov     [rbp+var_30], r12
0x180062e1f  mov     rax, [rcx]
0x180062e22  mov     [rsp+70h+pstmTemplate], rdx
0x180062e27  mov     edx, 0FFFFFFFCh
0x180062e2c  mov     rax, [rax+48h]
0x180062e30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062e35  mov     ebx, eax
0x180062e37  test    eax, eax
0x180062e39  js      loc_180062F4A
0x180062e3f  test    byte ptr [rbp+arg_8], 2
0x180062e43  jnz     loc_180062ED3
0x180062e49  mov     rcx, [rbp+var_30]
0x180062e4d  lea     rdx, [rbp+var_28]
0x180062e51  mov     [rbp+var_28], r12
0x180062e55  mov     rax, [rcx]
0x180062e58  mov     rax, [rax+118h]
0x180062e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062e64  mov     ebx, eax
0x180062e66  test    eax, eax
0x180062e68  js      loc_180062F4A
0x180062e6e  mov     rax, 346DC5D63886594Bh
0x180062e78  imul    [rbp+var_28]
0x180062e7c  sar     rdx, 0Bh
0x180062e80  mov     rax, rdx
0x180062e83  shr     rax, 3Fh
0x180062e87  add     rdx, rax
0x180062e8a  mov     [rbp+var_28], rdx
0x180062e8e  call    cs:__imp_GetTickCount64
0x180062e94  mov     rcx, [rbp+var_28]
0x180062e98  test    sil, sil
0x180062e9b  jz      short loc_180062EA3
0x180062e9d  mov     r15, rax
0x180062ea0  mov     r14, rcx
0x180062ea3  sub     rcx, rax
0x180062ea6  mov     sil, r12b
0x180062ea9  sub     rcx, r14
0x180062eac  add     rcx, r15; dwMilliseconds
0x180062eaf  js      loc_180062F4A
0x180062eb5  call    cs:__imp_Sleep
0x180062ebb  cmp     [rdi+18h], r12b
0x180062ebf  jz      loc_180062F4A
0x180062ec5  mov     rdx, [rbp+var_30]; struct IMFSample *
0x180062ec9  mov     rcx, rdi; this
0x180062ecc  call    ?_PresentSample@CLowResourceVideoPlayer@@AEAAJPEAUIMFSample@@@Z; CLowResourceVideoPlayer::_PresentSample(IMFSample *)
0x180062ed1  jmp     short loc_180062F4A
0x180062ed3  cmp     [rdi+38h], r12b
0x180062ed7  jz      short loc_180062F46
0x180062ed9  test    sil, sil
0x180062edc  jnz     short loc_180062F46
0x180062ede  cmp     [rdi+18h], r12b
0x180062ee2  jz      short loc_180062F4A
0x180062ee4  mov     rcx, [rbp+arg_18]
0x180062ee8  lea     r8, [rbp+var_18]
0x180062eec  xor     eax, eax
0x180062eee  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000
0x180062ef5  mov     [rbp+var_8], rax
0x180062ef9  xorps   xmm0, xmm0
0x180062efc  movups  [rbp+var_18], xmm0
0x180062f00  mov     eax, 14h
0x180062f05  mov     word ptr [rbp+var_18], ax
0x180062f09  mov     rax, [rcx]
0x180062f0c  mov     rax, [rax+40h]
0x180062f10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062f15  mov     ebx, eax
0x180062f17  test    eax, eax
0x180062f19  js      short loc_180062F4A
0x180062f1b  mov     sil, 1
0x180062f1e  call    cs:__imp_rand
0x180062f24  mov     ecx, eax
0x180062f26  mov     eax, 0D1B1B919h
0x180062f2b  mul     ecx
0x180062f2d  shr     edx, 0Dh
0x180062f30  imul    eax, edx, 2711h
0x180062f36  sub     ecx, eax
0x180062f38  add     ecx, 1388h; dwMilliseconds
0x180062f3e  call    cs:__imp_Sleep
0x180062f44  jmp     short loc_180062F4A
0x180062f46  mov     [rdi+18h], r12b
0x180062f4a  mov     rcx, [rbp+var_30]
0x180062f4e  test    rcx, rcx
0x180062f51  jz      short loc_180062F63
0x180062f53  mov     [rbp+var_30], r12
0x180062f57  mov     rax, [rcx]
0x180062f5a  mov     rax, [rax+10h]
0x180062f5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062f63  test    ebx, ebx
0x180062f65  jns     loc_180062DE4
0x180062f6b  call    cs:__imp_MFShutdown
0x180062f71  mov     rcx, [rbp+arg_18]
0x180062f75  test    rcx, rcx
0x180062f78  jz      short loc_180062F8A
0x180062f7a  mov     [rbp+arg_18], r12
0x180062f7e  mov     rax, [rcx]
0x180062f81  mov     rax, [rax+10h]
0x180062f85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062f8a  mov     eax, ebx
0x180062f8c  add     rsp, 70h
0x180062f90  pop     r15
0x180062f92  pop     r14
0x180062f94  pop     r12
0x180062f96  pop     rdi
0x180062f97  pop     rsi
0x180062f98  pop     rbx
0x180062f99  pop     rbp
0x180062f9a  retn
```
