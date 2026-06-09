# CContact::CommitChanges(ulong)

- ea: `0x18007c810`
- end: `0x18007ca06`
- name: `?CommitChanges@CContact@@UEAAJK@Z`
- size: `502`
- prototype: `__int64 __fastcall(CContact *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002818`
- `0x18007c810`
- `0x18008f9fc`
- `0x180091ef0`
- `0x180093010`

## import_xrefs

- `MSOERT2!OpenFileStreamShareW` at `0x18007c91c`
- `MSOERT2!OpenFileStreamShareW` at `0x18007c91c`
- `SHLWAPI!__imp_SHCreateMemStream` at `0x18007c8b1`
- `SHLWAPI!__imp_SHCreateMemStream` at `0x18007c8b1`
- `SHLWAPI!__imp_IStream_Size` at `0x18007c96e`
- `SHLWAPI!__imp_IStream_Size` at `0x18007c96e`
- `KERNEL32!GetCurrentThreadId` at `0x18007c854`
- `KERNEL32!GetCurrentThreadId` at `0x18007c854`

## pseudocode

```c
__int64 __fastcall CContact::CommitChanges(struct _GUID *this, int a2)
{
  int v2; // ebx
  HRESULT v5; // ebx
  IStream *v6; // rax
  IStream *v7; // rsi
  const WCHAR *v8; // rcx
  __int64 v9; // rax
  struct IStream *v11; // [rsp+30h] [rbp-38h] BYREF
  ULARGE_INTEGER pui; // [rsp+38h] [rbp-30h] BYREF
  IStream *v13; // [rsp+40h] [rbp-28h] BYREF
  struct _GUID v14; // [rsp+48h] [rbp-20h] BYREF

  v2 = *(_DWORD *)this[44].Data4;
  v14 = 0;
  pui.QuadPart = 0;
  v13 = 0;
  v11 = 0;
  if ( GetCurrentThreadId() != v2 )
  {
    v5 = -2147417842;
    goto LABEL_26;
  }
  if ( a2 )
  {
    v5 = -2147024809;
    goto LABEL_26;
  }
  if ( !*(_DWORD *)this[4].Data4 || !*(_DWORD *)this[37].Data4 )
  {
    v5 = -2147418113;
    goto LABEL_26;
  }
  if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)this[41].Data4 + 136LL))(*(_QWORD *)this[41].Data4) )
  {
LABEL_25:
    v5 = 0;
    goto LABEL_26;
  }
  v6 = SHCreateMemStream(0, 0);
  v13 = v6;
  v7 = v6;
  if ( !v6 )
  {
    v5 = -2147024882;
    goto LABEL_26;
  }
  v5 = (*(__int64 (__fastcall **)(struct _GUID *, IStream *, _QWORD))(*(_QWORD *)&this[2].Data1 + 48LL))(
         this + 2,
         v6,
         0);
  if ( v5 >= 0 )
  {
    v8 = &Str;
    if ( *(_DWORD *)this[37].Data4 )
      v8 = *(const WCHAR **)&this[38].Data1;
    v5 = OpenFileStreamShareW(v8, 3, 3221225472LL, 4, &v11);
    if ( v5 >= 0 )
    {
      v5 = HashStreamMD5(v11, &v14);
      if ( v5 >= 0 )
      {
        v9 = *(_QWORD *)&v14.Data1 - *(_QWORD *)&this[40].Data1;
        if ( *(_QWORD *)&v14.Data1 == *(_QWORD *)&this[40].Data1 )
          v9 = *(_QWORD *)v14.Data4 - *(_QWORD *)this[40].Data4;
        if ( v9 )
        {
          v5 = -2147024681;
          goto LABEL_26;
        }
        v5 = IStream_Size(v7, &pui);
        if ( v5 >= 0 )
        {
          v5 = HashStreamMD5(v7, &v14);
          if ( v5 >= 0 )
          {
            v5 = (*(__int64 (__fastcall **)(struct IStream *, ULARGE_INTEGER))(*(_QWORD *)v11 + 48LL))(v11, pui);
            if ( v5 >= 0 )
            {
              v5 = (*(__int64 (__fastcall **)(IStream *, struct IStream *, ULARGE_INTEGER, _QWORD, _QWORD))(*(_QWORD *)v7 + 56LL))(
                     v7,
                     v11,
                     pui,
                     0,
                     0);
              if ( v5 >= 0 )
              {
                this[40] = v14;
                goto LABEL_25;
              }
            }
          }
        }
      }
    }
  }
LABEL_26:
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v11);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v13);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18007c810  push    rbp
0x18007c812  push    rbx
0x18007c813  push    rsi
0x18007c814  push    rdi
0x18007c815  mov     rbp, rsp
0x18007c818  sub     rsp, 68h
0x18007c81c  mov     rax, cs:__security_cookie
0x18007c823  xor     rax, rsp
0x18007c826  mov     [rbp+var_10], rax
0x18007c82a  mov     ebx, [rcx+2C8h]
0x18007c830  xorps   xmm0, xmm0
0x18007c833  movups  xmmword ptr [rbp+var_20.Data1], xmm0
0x18007c837  mov     esi, edx
0x18007c839  mov     qword ptr [rbp+pui], 0
0x18007c841  mov     rdi, rcx
0x18007c844  mov     [rbp+var_28], 0
0x18007c84c  mov     [rbp+var_38], 0
0x18007c854  call    cs:__imp_GetCurrentThreadId
0x18007c85a  cmp     eax, ebx
0x18007c85c  jz      short loc_18007C868
0x18007c85e  mov     ebx, 8001010Eh
0x18007c863  jmp     loc_18007C9DD
0x18007c868  test    esi, esi
0x18007c86a  jz      short loc_18007C876
0x18007c86c  mov     ebx, 80070057h
0x18007c871  jmp     loc_18007C9DD
0x18007c876  cmp     dword ptr [rdi+48h], 0
0x18007c87a  jnz     short loc_18007C886
0x18007c87c  mov     ebx, 8000FFFFh
0x18007c881  jmp     loc_18007C9DD
0x18007c886  cmp     dword ptr [rdi+258h], 0
0x18007c88d  jz      short loc_18007C87C
0x18007c88f  mov     rcx, [rdi+298h]
0x18007c896  mov     rax, [rcx]
0x18007c899  mov     rax, [rax+88h]
0x18007c8a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c8a5  test    eax, eax
0x18007c8a7  jnz     loc_18007C9DB
0x18007c8ad  xor     edx, edx; cbInit
0x18007c8af  xor     ecx, ecx; pInit
0x18007c8b1  call    cs:__imp_SHCreateMemStream
0x18007c8b7  mov     [rbp+var_28], rax
0x18007c8bb  mov     rsi, rax
0x18007c8be  test    rax, rax
0x18007c8c1  jnz     short loc_18007C8CD
0x18007c8c3  mov     ebx, 8007000Eh
0x18007c8c8  jmp     loc_18007C9DD
0x18007c8cd  lea     rcx, [rdi+20h]
0x18007c8d1  xor     r8d, r8d
0x18007c8d4  mov     rax, [rcx]
0x18007c8d7  mov     rdx, rsi
0x18007c8da  mov     rax, [rax+30h]
0x18007c8de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c8e3  mov     ebx, eax
0x18007c8e5  test    eax, eax
0x18007c8e7  js      loc_18007C9DD
0x18007c8ed  cmp     dword ptr [rdi+258h], 0
0x18007c8f4  lea     rcx, Str
0x18007c8fb  jz      short loc_18007C904
0x18007c8fd  mov     rcx, [rdi+260h]
0x18007c904  mov     edx, 3
0x18007c909  lea     rax, [rbp+var_38]
0x18007c90d  mov     r8d, 0C0000000h
0x18007c913  mov     [rsp+68h+var_48], rax
0x18007c918  lea     r9d, [rdx+1]
0x18007c91c  call    cs:__imp_OpenFileStreamShareW
0x18007c922  mov     ebx, eax
0x18007c924  test    eax, eax
0x18007c926  js      loc_18007C9DD
0x18007c92c  mov     rcx, [rbp+var_38]; struct IStream *
0x18007c930  lea     rdx, [rbp+var_20]; struct _GUID *
0x18007c934  call    ?HashStreamMD5@@YAJPEAUIStream@@PEAU_GUID@@@Z; HashStreamMD5(IStream *,_GUID *)
0x18007c939  mov     ebx, eax
0x18007c93b  test    eax, eax
0x18007c93d  js      loc_18007C9DD
0x18007c943  mov     rax, qword ptr [rbp+var_20.Data1]
0x18007c947  sub     rax, [rdi+280h]
0x18007c94e  jnz     short loc_18007C95B
0x18007c950  mov     rax, qword ptr [rbp+var_20.Data4]
0x18007c954  sub     rax, [rdi+288h]
0x18007c95b  test    rax, rax
0x18007c95e  jz      short loc_18007C967
0x18007c960  mov     ebx, 800700D7h
0x18007c965  jmp     short loc_18007C9DD
0x18007c967  lea     rdx, [rbp+pui]; pui
0x18007c96b  mov     rcx, rsi; pstm
0x18007c96e  call    cs:__imp_IStream_Size
0x18007c974  mov     ebx, eax
0x18007c976  test    eax, eax
0x18007c978  js      short loc_18007C9DD
0x18007c97a  lea     rdx, [rbp+var_20]; struct _GUID *
0x18007c97e  mov     rcx, rsi; struct IStream *
0x18007c981  call    ?HashStreamMD5@@YAJPEAUIStream@@PEAU_GUID@@@Z; HashStreamMD5(IStream *,_GUID *)
0x18007c986  mov     ebx, eax
0x18007c988  test    eax, eax
0x18007c98a  js      short loc_18007C9DD
0x18007c98c  mov     rcx, [rbp+var_38]
0x18007c990  mov     rdx, qword ptr [rbp+pui]
0x18007c994  mov     rax, [rcx]
0x18007c997  mov     rax, [rax+30h]
0x18007c99b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c9a0  mov     ebx, eax
0x18007c9a2  test    eax, eax
0x18007c9a4  js      short loc_18007C9DD
0x18007c9a6  mov     rax, [rsi]
0x18007c9a9  xor     r9d, r9d
0x18007c9ac  mov     r8, qword ptr [rbp+pui]
0x18007c9b0  mov     rcx, rsi
0x18007c9b3  mov     rdx, [rbp+var_38]
0x18007c9b7  mov     [rsp+68h+var_48], 0
0x18007c9c0  mov     rax, [rax+38h]
0x18007c9c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c9c9  mov     ebx, eax
0x18007c9cb  test    eax, eax
0x18007c9cd  js      short loc_18007C9DD
0x18007c9cf  movups  xmm0, xmmword ptr [rbp+var_20.Data1]
0x18007c9d3  movdqu  xmmword ptr [rdi+280h], xmm0
0x18007c9db  xor     ebx, ebx
0x18007c9dd  lea     rcx, [rbp+var_38]
0x18007c9e1  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18007c9e6  lea     rcx, [rbp+var_28]
0x18007c9ea  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18007c9ef  mov     eax, ebx
0x18007c9f1  mov     rcx, [rbp+var_10]
0x18007c9f5  xor     rcx, rsp; StackCookie
0x18007c9f8  call    __security_check_cookie
0x18007c9fd  add     rsp, 68h
0x18007ca01  pop     rdi
0x18007ca02  pop     rsi
0x18007ca03  pop     rbx
0x18007ca04  pop     rbp
0x18007ca05  retn
```
