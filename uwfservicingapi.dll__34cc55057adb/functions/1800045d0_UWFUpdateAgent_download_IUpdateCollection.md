# UWFUpdateAgent::download(IUpdateCollection *)

- ea: `0x1800045d0`
- end: `0x180004904`
- name: `?download@UWFUpdateAgent@@AEAAJPEAUIUpdateCollection@@@Z`
- size: `820`
- prototype: `__int64 __fastcall(UWFUpdateAgent *__hidden this, struct IUpdateCollection *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update`

## callers

- `0x18000399c`

## callees

- `0x180002570`
- `0x180002a20`
- `0x1800045d0`
- `0x180004f50`
- `0x180005175`
- `0x1800051a0`
- `0x180006010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180004809`
- `msvcrt!wcscat_s` at `0x180004809`
- `msvcrt!swprintf_s` at `0x1800047e1`
- `msvcrt!swprintf_s` at `0x1800047e1`

## string_xrefs

- `0x1800048c4`: `CreateUpdateDownloader failed`
- `0x18000465e`: `UpdateDownloader put_Updates failed`
- `0x180004868`: `Update download failure`

## pseudocode

```c
__int64 __fastcall UWFUpdateAgent::download(UWFUpdateAgent *this, struct IUpdateCollection *a2)
{
  int v4; // edi
  struct IUpdateCollectionVtbl *lpVtbl; // rax
  unsigned __int64 v6; // rax
  const wchar_t *v7; // r9
  unsigned int v8; // esi
  int v9; // eax
  struct IUpdateCollectionVtbl *v10; // rax
  UWFUpdateAgent *v11; // rcx
  int v12; // r9d
  __int64 v13; // r8
  unsigned int v15; // [rsp+20h] [rbp-E0h] BYREF
  int v16; // [rsp+24h] [rbp-DCh] BYREF
  __int64 v17; // [rsp+28h] [rbp-D8h] BYREF
  struct IUpdate *v18; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v19; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t Buffer[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v22[508]; // [rsp+54h] [rbp-ACh] BYREF
  wchar_t Source[2]; // [rsp+250h] [rbp+150h] BYREF
  _BYTE v24[508]; // [rsp+254h] [rbp+154h] BYREF

  v17 = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 1) + 104LL))(*((_QWORD *)this + 1), &v17);
  if ( v4 < 0 || !v17 )
  {
    UwfServicingLog(1, 1, (unsigned int)v4, L"CreateUpdateDownloader failed");
    return (unsigned int)v4;
  }
  v4 = (*(__int64 (__fastcall **)(__int64, struct IUpdateCollection *))(*(_QWORD *)v17 + 112LL))(v17, a2);
  if ( v4 < 0 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    UwfServicingLog(1, 1, (unsigned int)v4, L"UpdateDownloader put_Updates failed");
    return (unsigned int)v4;
  }
  lpVtbl = a2->lpVtbl;
  v16 = 0;
  v19 = 0;
  v20 = 0;
  v4 = ((__int64 (__fastcall *)(struct IUpdateCollection *, int *))lpVtbl->get_Count)(a2, &v16);
  if ( v4 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v17 + 128LL))(v17, &v19);
    if ( v4 < 0 )
    {
      v7 = L"Update download failure";
      goto LABEL_23;
    }
    v6 = 4LL * v16;
    if ( !is_mul_ok(v16, 4u) )
      v6 = -1;
    *(_QWORD *)(*((_QWORD *)this + 2) + 24LL) = operator new[](v6, (const struct std::nothrow_t *)&std::nothrow);
    if ( !*(_QWORD *)(*((_QWORD *)this + 2) + 24LL) )
    {
      v7 = L"Memory allocation failure";
LABEL_23:
      v13 = (unsigned int)v4;
LABEL_24:
      UwfServicingLog(1, 1, v13, v7);
      goto LABEL_25;
    }
    v8 = 0;
    if ( v16 > 0 )
    {
      while ( 1 )
      {
        v15 = 0;
        v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v19 + 72LL))(v19, v8, &v20);
        v4 = v9;
        if ( v9 < 0 )
          break;
        v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v20 + 64LL))(v20, &v15);
        v4 = v9;
        if ( v9 < 0 )
        {
          v7 = L"Failed to get download result code";
          goto LABEL_20;
        }
        v10 = a2->lpVtbl;
        v18 = 0;
        v4 = ((__int64 (__fastcall *)(struct IUpdateCollection *, _QWORD, struct IUpdate **))v10->get_Item)(
               a2,
               v8,
               &v18);
        if ( v4 >= 0 && v15 != 2 )
        {
          *(_DWORD *)Source = 0;
          memset_0(v24, 0, sizeof(v24));
          *(_DWORD *)Buffer = 0;
          memset_0(v22, 0, sizeof(v22));
          swprintf_s(Buffer, 0x100u, L"Download Error ");
          UWFUpdateAgent::printTitleAndKBNumber(v11, v18, Source, v12);
          wcscat_s(Buffer, 0x100u, Source);
          UwfServicingLog(1, 0, v15, Buffer);
        }
        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 2) + 24LL) + 4LL * (int)v8) = v15;
        ((void (__fastcall *)(struct IUpdate *))v18->lpVtbl->Release)(v18);
        if ( (int)++v8 >= v16 )
          goto LABEL_25;
      }
      v7 = L"Failed to get download results";
LABEL_20:
      v13 = (unsigned int)v9;
      goto LABEL_24;
    }
  }
LABEL_25:
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800045d0  mov     [rsp-8+arg_10], rbx
0x1800045d5  push    rbp
0x1800045d6  push    rsi
0x1800045d7  push    rdi
0x1800045d8  push    r14
0x1800045da  push    r15
0x1800045dc  lea     rbp, [rsp-360h]
0x1800045e4  sub     rsp, 460h
0x1800045eb  mov     rax, cs:__security_cookie
0x1800045f2  xor     rax, rsp
0x1800045f5  mov     [rbp+380h+var_30], rax
0x1800045fc  mov     r15, rcx
0x1800045ff  mov     [rsp+480h+var_458], 0
0x180004608  mov     rcx, [rcx+8]
0x18000460c  mov     r14, rdx
0x18000460f  lea     rdx, [rsp+480h+var_458]
0x180004614  mov     rax, [rcx]
0x180004617  mov     rax, [rax+68h]
0x18000461b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004620  mov     edi, eax
0x180004622  test    eax, eax
0x180004624  js      loc_1800048C4
0x18000462a  mov     rcx, [rsp+480h+var_458]
0x18000462f  test    rcx, rcx
0x180004632  jz      loc_1800048C4
0x180004638  mov     rax, [rcx]
0x18000463b  mov     rdx, r14
0x18000463e  mov     rax, [rax+70h]
0x180004642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004647  mov     edi, eax
0x180004649  test    eax, eax
0x18000464b  jns     short loc_18000466A
0x18000464d  mov     rcx, [rsp+480h+var_458]
0x180004652  mov     rdx, [rcx]
0x180004655  mov     rax, [rdx+10h]
0x180004659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000465e  lea     r9, aUpdatedownload; "UpdateDownloader put_Updates failed"
0x180004665  jmp     loc_1800048CB
0x18000466a  mov     rax, [r14]
0x18000466d  lea     rdx, [rsp+480h+var_45C]
0x180004672  mov     rcx, r14
0x180004675  mov     [rsp+480h+var_45C], 0
0x18000467d  mov     [rsp+480h+var_448], 0
0x180004686  mov     [rsp+480h+var_440], 0
0x18000468f  mov     rax, [rax+50h]
0x180004693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004698  mov     edi, eax
0x18000469a  test    eax, eax
0x18000469c  js      loc_180004880
0x1800046a2  mov     rcx, [rsp+480h+var_458]
0x1800046a7  lea     rdx, [rsp+480h+var_448]
0x1800046ac  mov     rax, [rcx]
0x1800046af  mov     rax, [rax+80h]
0x1800046b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046bb  mov     edi, eax
0x1800046bd  test    eax, eax
0x1800046bf  js      loc_180004868
0x1800046c5  movsxd  rcx, [rsp+480h+var_45C]
0x1800046ca  mov     eax, 4
0x1800046cf  mul     rcx
0x1800046d2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800046d9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800046e0  cmovb   rax, rcx
0x1800046e4  mov     rcx, rax; unsigned __int64
0x1800046e7  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800046ec  mov     rcx, [r15+10h]
0x1800046f0  mov     [rcx+18h], rax
0x1800046f4  mov     rax, [r15+10h]
0x1800046f8  cmp     qword ptr [rax+18h], 0
0x1800046fd  jnz     short loc_18000470B
0x1800046ff  lea     r9, aMemoryAllocati; "Memory allocation failure"
0x180004706  jmp     loc_18000486F
0x18000470b  xor     esi, esi
0x18000470d  cmp     [rsp+480h+var_45C], esi
0x180004711  jle     loc_180004880
0x180004717  lea     ebx, [rsi+1]
0x18000471a  mov     rcx, [rsp+480h+var_448]
0x18000471f  lea     r8, [rsp+480h+var_440]
0x180004724  mov     [rsp+480h+var_460], 0
0x18000472c  mov     edx, esi
0x18000472e  mov     rax, [rcx]
0x180004731  mov     rax, [rax+48h]
0x180004735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000473a  mov     edi, eax
0x18000473c  test    eax, eax
0x18000473e  js      loc_18000485F
0x180004744  mov     rcx, [rsp+480h+var_440]
0x180004749  lea     rdx, [rsp+480h+var_460]
0x18000474e  mov     rax, [rcx]
0x180004751  mov     rax, [rax+40h]
0x180004755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000475a  mov     edi, eax
0x18000475c  test    eax, eax
0x18000475e  js      loc_180004853
0x180004764  mov     rax, [r14]
0x180004767  lea     r8, [rsp+480h+var_450]
0x18000476c  mov     edx, esi
0x18000476e  mov     [rsp+480h+var_450], 0
0x180004777  mov     rcx, r14
0x18000477a  mov     rax, [rax+38h]
0x18000477e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004783  mov     edi, eax
0x180004785  test    eax, eax
0x180004787  js      loc_180004822
0x18000478d  cmp     [rsp+480h+var_460], 2
0x180004792  jz      loc_180004822
0x180004798  xor     edx, edx; Val
0x18000479a  mov     dword ptr [rbp+380h+Source], 0
0x1800047a4  mov     r8d, 1FCh; Size
0x1800047aa  lea     rcx, [rbp+380h+var_22C]; void *
0x1800047b1  call    memset_0
0x1800047b6  xor     edx, edx; Val
0x1800047b8  mov     dword ptr [rsp+480h+Buffer], 0
0x1800047c0  mov     r8d, 1FCh; Size
0x1800047c6  lea     rcx, [rsp+480h+var_42C]; void *
0x1800047cb  call    memset_0
0x1800047d0  lea     r8, aDownloadError; "Download Error "
0x1800047d7  mov     edx, 100h; BufferCount
0x1800047dc  lea     rcx, [rsp+480h+Buffer]; Buffer
0x1800047e1  call    cs:__imp_swprintf_s
0x1800047e7  mov     rdx, [rsp+480h+var_450]; struct IUpdate *
0x1800047ec  lea     r8, [rbp+380h+Source]; unsigned __int16 *
0x1800047f3  call    ?printTitleAndKBNumber@UWFUpdateAgent@@AEAAJPEAUIUpdate@@PEAGJ@Z; UWFUpdateAgent::printTitleAndKBNumber(IUpdate *,ushort *,long)
0x1800047f8  lea     r8, [rbp+380h+Source]; Source
0x1800047ff  mov     edx, 100h; SizeInWords
0x180004804  lea     rcx, [rsp+480h+Buffer]; Destination
0x180004809  call    cs:__imp_wcscat_s
0x18000480f  mov     r8d, [rsp+480h+var_460]
0x180004814  lea     r9, [rsp+480h+Buffer]
0x180004819  xor     edx, edx
0x18000481b  mov     ecx, ebx
0x18000481d  call    ?UwfServicingLog@@YAJW4UWFSERVICING_MODULE_ID@@W4UWFSERVICING_LOG_TYPE@@KPEBGZZ; UwfServicingLog(UWFSERVICING_MODULE_ID,UWFSERVICING_LOG_TYPE,ulong,ushort const *,...)
0x180004822  mov     rax, [r15+10h]
0x180004826  movsxd  rdx, esi
0x180004829  mov     rcx, [rax+18h]
0x18000482d  mov     eax, [rsp+480h+var_460]
0x180004831  mov     [rcx+rdx*4], eax
0x180004834  mov     rcx, [rsp+480h+var_450]
0x180004839  mov     rax, [rcx]
0x18000483c  mov     rax, [rax+10h]
0x180004840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004845  add     esi, ebx
0x180004847  cmp     esi, [rsp+480h+var_45C]
0x18000484b  jl      loc_18000471A
0x180004851  jmp     short loc_180004880
0x180004853  lea     r9, aFailedToGetDow_0; "Failed to get download result code"
0x18000485a  mov     r8d, eax
0x18000485d  jmp     short loc_180004877
0x18000485f  lea     r9, aFailedToGetDow; "Failed to get download results"
0x180004866  jmp     short loc_18000485A
0x180004868  lea     r9, aUpdateDownload; "Update download failure"
0x18000486f  mov     ebx, 1
0x180004874  mov     r8d, edi
0x180004877  mov     edx, ebx
0x180004879  mov     ecx, ebx
0x18000487b  call    ?UwfServicingLog@@YAJW4UWFSERVICING_MODULE_ID@@W4UWFSERVICING_LOG_TYPE@@KPEBGZZ; UwfServicingLog(UWFSERVICING_MODULE_ID,UWFSERVICING_LOG_TYPE,ulong,ushort const *,...)
0x180004880  mov     rcx, [rsp+480h+var_458]
0x180004885  test    rcx, rcx
0x180004888  jz      short loc_180004896
0x18000488a  mov     rax, [rcx]
0x18000488d  mov     rax, [rax+10h]
0x180004891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004896  mov     rcx, [rsp+480h+var_448]
0x18000489b  test    rcx, rcx
0x18000489e  jz      short loc_1800048AC
0x1800048a0  mov     rax, [rcx]
0x1800048a3  mov     rax, [rax+10h]
0x1800048a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048ac  mov     rcx, [rsp+480h+var_440]
0x1800048b1  test    rcx, rcx
0x1800048b4  jz      short loc_1800048DC
0x1800048b6  mov     rax, [rcx]
0x1800048b9  mov     rax, [rax+10h]
0x1800048bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048c2  jmp     short loc_1800048DC
0x1800048c4  lea     r9, aCreateupdatedo; "CreateUpdateDownloader failed"
0x1800048cb  mov     ebx, 1
0x1800048d0  mov     r8d, edi
0x1800048d3  mov     edx, ebx
0x1800048d5  mov     ecx, ebx
0x1800048d7  call    ?UwfServicingLog@@YAJW4UWFSERVICING_MODULE_ID@@W4UWFSERVICING_LOG_TYPE@@KPEBGZZ; UwfServicingLog(UWFSERVICING_MODULE_ID,UWFSERVICING_LOG_TYPE,ulong,ushort const *,...)
0x1800048dc  mov     eax, edi
0x1800048de  mov     rcx, [rbp+380h+var_30]
0x1800048e5  xor     rcx, rsp; StackCookie
0x1800048e8  call    __security_check_cookie
0x1800048ed  mov     rbx, [rsp+480h+arg_10]
0x1800048f5  add     rsp, 460h
0x1800048fc  pop     r15
0x1800048fe  pop     r14
0x180004900  pop     rdi
0x180004901  pop     rsi
0x180004902  pop     rbp
0x180004903  retn
```
