# std::_Variant_destroy_layer_<windiag::win_handle<void *,windiag::close_handle,0>,windiag::win_handle<void *,windiag::close_handle,-1>,windiag::win_handle<HINSTANCE__ *,windiag::close_dll,0>,windiag::win_handle<SC_HANDLE__ *,windiag::close_scm,0>,windiag::win_handle<void *,windiag::close_hlocal,0>,windiag::win_handle<HKEY__ *,windiag::close_hkey,0>>::~_Variant_destroy_layer_<windiag::win_handle<void *,windiag::close_handle,0>,windiag::win_handle<void *,windiag::close_handle,-1>,windiag::win_handle<HINSTANCE__ *,windiag::close_dll,0>,windiag::win_handle<SC_HANDLE__ *,windiag::close_scm,0>,windiag::win_handle<void *,windiag::close_hlocal,0>,windiag::win_handle<HKEY__ *,windiag::close_hkey,0>>(void)

- ea: `0x180079814`
- end: `0x1800798dc`
- name: `??1?$_Variant_destroy_layer_@U?$win_handle@PEAXUclose_handle@windiag@@$0A@@windiag@@U?$win_handle@PEAXUclose_handle@windiag@@$0?0@2@U?$win_handle@PEAUHINSTANCE__@@Uclose_dll@windiag@@$0A@@2@U?$win_handle@PEAUSC_HANDLE__@@Uclose_scm@windiag@@$0A@@2@U?$win_handle@PEAXUclose_hlocal@windiag@@$0A@@2@U?$win_handle@PEAUHKEY__@@Uclose_hkey@windiag@@$0A@@2@@std@@QEAA@XZ`
- size: `200`
- prototype: `int __fastcall(__int64)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180079614`
- `0x1800798e4`
- `0x18007a220`
- `0x18007a8b0`
- `0x18007a9b0`

## callees

- `0x180079814`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180079899`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180079899`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800798ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800798c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800798ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800798c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180079871`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180079871`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180079885`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180079885`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007985d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007985d`

## pseudocode

```c
int __fastcall std::_Variant_destroy_layer_<windiag::win_handle<void *,windiag::close_handle,0>,windiag::win_handle<void *,windiag::close_handle,-1>,windiag::win_handle<HINSTANCE__ *,windiag::close_dll,0>,windiag::win_handle<SC_HANDLE__ *,windiag::close_scm,0>,windiag::win_handle<void *,windiag::close_hlocal,0>,windiag::win_handle<HKEY__ *,windiag::close_hkey,0>>::~_Variant_destroy_layer_<windiag::win_handle<void *,windiag::close_handle,0>,windiag::win_handle<void *,windiag::close_handle,-1>,windiag::win_handle<HINSTANCE__ *,windiag::close_dll,0>,windiag::win_handle<SC_HANDLE__ *,windiag::close_scm,0>,windiag::win_handle<void *,windiag::close_hlocal,0>,windiag::win_handle<HKEY__ *,windiag::close_hkey,0>>(
        __int64 a1)
{
  __int64 v2; // rax
  HMODULE v3; // rcx

  v2 = *(char *)(a1 + 8) + 1LL;
  if ( *(char *)(a1 + 8) != -1 )
  {
    v3 = *(HMODULE *)a1;
    if ( !--v2 )
    {
      if ( v3 )
      {
        *(_QWORD *)a1 = 0;
        LODWORD(v2) = CloseHandle(v3);
      }
      goto LABEL_20;
    }
    if ( --v2 )
    {
      if ( --v2 )
      {
        if ( --v2 )
        {
          if ( v2 == 1 )
          {
            if ( v3 )
            {
              *(_QWORD *)a1 = 0;
              LODWORD(v2) = (unsigned int)LocalFree(v3);
            }
          }
          else if ( v3 )
          {
            *(_QWORD *)a1 = 0;
            LODWORD(v2) = RegCloseKey((HKEY)v3);
          }
        }
        else if ( v3 )
        {
          *(_QWORD *)a1 = 0;
          LODWORD(v2) = CloseServiceHandle((SC_HANDLE)v3);
        }
      }
      else if ( v3 )
      {
        *(_QWORD *)a1 = 0;
        LODWORD(v2) = FreeLibrary(v3);
      }
LABEL_20:
      *(_QWORD *)a1 = 0;
      return v2;
    }
    if ( v3 != (HMODULE)-1LL )
    {
      *(_QWORD *)a1 = -1;
      LODWORD(v2) = CloseHandle(v3);
    }
    *(_QWORD *)a1 = -1;
  }
  return v2;
}

```

## disassembly

```asm
0x180079814  push    rbx
0x180079816  sub     rsp, 20h
0x18007981a  movsx   rax, byte ptr [rcx+8]
0x18007981f  mov     rbx, rcx
0x180079822  add     rax, 1
0x180079826  jz      loc_1800798D6
0x18007982c  mov     rcx, [rcx]; hObject
0x18007982f  sub     rax, 1
0x180079833  jz      loc_1800798BD
0x180079839  sub     rax, 1
0x18007983d  jz      short loc_1800798A1
0x18007983f  sub     rax, 1
0x180079843  jz      short loc_18007988D
0x180079845  sub     rax, 1
0x180079849  jz      short loc_180079879
0x18007984b  cmp     rax, 1
0x18007984f  jz      short loc_180079865
0x180079851  test    rcx, rcx
0x180079854  jz      short loc_1800798CF
0x180079856  mov     qword ptr [rbx], 0
0x18007985d  call    cs:__imp_RegCloseKey
0x180079863  jmp     short loc_1800798CF
0x180079865  test    rcx, rcx
0x180079868  jz      short loc_1800798CF
0x18007986a  mov     qword ptr [rbx], 0
0x180079871  call    cs:__imp_LocalFree
0x180079877  jmp     short loc_1800798CF
0x180079879  test    rcx, rcx
0x18007987c  jz      short loc_1800798CF
0x18007987e  mov     qword ptr [rbx], 0
0x180079885  call    cs:__imp_CloseServiceHandle
0x18007988b  jmp     short loc_1800798CF
0x18007988d  test    rcx, rcx
0x180079890  jz      short loc_1800798CF
0x180079892  mov     qword ptr [rbx], 0
0x180079899  call    cs:__imp_FreeLibrary
0x18007989f  jmp     short loc_1800798CF
0x1800798a1  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800798a5  jz      short loc_1800798B4
0x1800798a7  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x1800798ae  call    cs:__imp_CloseHandle
0x1800798b4  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x1800798bb  jmp     short loc_1800798D6
0x1800798bd  test    rcx, rcx
0x1800798c0  jz      short loc_1800798CF
0x1800798c2  mov     qword ptr [rbx], 0
0x1800798c9  call    cs:__imp_CloseHandle
0x1800798cf  mov     qword ptr [rbx], 0
0x1800798d6  add     rsp, 20h
0x1800798da  pop     rbx
0x1800798db  retn
```
