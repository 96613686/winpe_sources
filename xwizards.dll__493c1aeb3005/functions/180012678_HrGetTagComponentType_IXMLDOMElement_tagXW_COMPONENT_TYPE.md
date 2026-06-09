# HrGetTagComponentType(IXMLDOMElement *,tagXW_COMPONENT_TYPE *)

- ea: `0x180012678`
- end: `0x180012797`
- name: `?HrGetTagComponentType@@YAJPEAUIXMLDOMElement@@PEAW4tagXW_COMPONENT_TYPE@@@Z`
- size: `287`
- prototype: `__int64 __fastcall(struct IXMLDOMElement *, enum tagXW_COMPONENT_TYPE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180013994`

## callees

- `0x18000ae04`
- `0x18000ae90`
- `0x180012678`
- `0x180034010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800126c9`
- `msvcrt!_wcsicmp` at `0x1800126e7`
- `msvcrt!_wcsicmp` at `0x180012705`
- `msvcrt!_wcsicmp` at `0x1800126c9`
- `msvcrt!_wcsicmp` at `0x1800126e7`
- `msvcrt!_wcsicmp` at `0x180012705`
- `OLEAUT32!__imp_SysFreeString` at `0x180012755`
- `OLEAUT32!__imp_SysFreeString` at `0x180012755`

## pseudocode

```c
__int64 __fastcall HrGetTagComponentType(struct IXMLDOMElement *a1, enum tagXW_COMPONENT_TYPE *a2)
{
  struct IXMLDOMElementVtbl *lpVtbl; // rax
  int v4; // edi
  wchar_t *String2; // [rsp+40h] [rbp+8h] BYREF

  *(_DWORD *)a2 = 0;
  lpVtbl = a1->lpVtbl;
  String2 = 0;
  v4 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, wchar_t **))lpVtbl->get_tagName)(a1, &String2);
  if ( v4 >= 0 )
  {
    if ( _wcsicmp(L"host", String2) )
    {
      if ( _wcsicmp(L"task", String2) )
      {
        if ( _wcsicmp(L"page", String2) )
        {
          v4 = -2147418113;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_SD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              16,
              (unsigned int)&WPP_92b4ede73d0c3990e751819403b3312f_Traceguids,
              (_DWORD)String2,
              255);
        }
        else
        {
          *(_DWORD *)a2 = 3;
        }
      }
      else
      {
        *(_DWORD *)a2 = 2;
      }
    }
    else
    {
      *(_DWORD *)a2 = 1;
    }
    SysFreeString(String2);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids,
      (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180012678  mov     r11, rsp
0x18001267b  mov     [r11+10h], rbx
0x18001267f  mov     [r11+18h], rsi
0x180012683  push    rdi
0x180012684  sub     rsp, 30h
0x180012688  mov     dword ptr [rdx], 0
0x18001268e  mov     rbx, rdx
0x180012691  mov     rax, [rcx]
0x180012694  lea     rdx, [r11+8]
0x180012698  mov     qword ptr [r11+8], 0
0x1800126a0  mov     rax, [rax+158h]
0x1800126a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126ac  lea     rsi, WPP_GLOBAL_Control
0x1800126b3  mov     edi, eax
0x1800126b5  test    eax, eax
0x1800126b7  js      loc_18001275B
0x1800126bd  mov     rdx, [rsp+38h+String2]; String2
0x1800126c2  lea     rcx, aHost; "host"
0x1800126c9  call    cs:__imp__wcsicmp
0x1800126cf  test    eax, eax
0x1800126d1  jnz     short loc_1800126DB
0x1800126d3  mov     dword ptr [rbx], 1
0x1800126d9  jmp     short loc_180012750
0x1800126db  mov     rdx, [rsp+38h+String2]; String2
0x1800126e0  lea     rcx, aTask; "task"
0x1800126e7  call    cs:__imp__wcsicmp
0x1800126ed  test    eax, eax
0x1800126ef  jnz     short loc_1800126F9
0x1800126f1  mov     dword ptr [rbx], 2
0x1800126f7  jmp     short loc_180012750
0x1800126f9  mov     rdx, [rsp+38h+String2]; String2
0x1800126fe  lea     rcx, aPage; "page"
0x180012705  call    cs:__imp__wcsicmp
0x18001270b  test    eax, eax
0x18001270d  jnz     short loc_180012717
0x18001270f  mov     dword ptr [rbx], 3
0x180012715  jmp     short loc_180012750
0x180012717  mov     edi, 8000FFFFh
0x18001271c  mov     rcx, cs:WPP_GLOBAL_Control
0x180012723  cmp     rcx, rsi
0x180012726  jz      short loc_180012750
0x180012728  test    byte ptr [rcx+1Ch], 8
0x18001272c  jz      short loc_180012750
0x18001272e  mov     r9, [rsp+38h+String2]
0x180012733  lea     r8, WPP_92b4ede73d0c3990e751819403b3312f_Traceguids
0x18001273a  mov     rcx, [rcx+10h]
0x18001273e  mov     edx, 10h
0x180012743  mov     [rsp+38h+var_18], 8000FFFFh
0x18001274b  call    WPP_SF_SD
0x180012750  mov     rcx, [rsp+38h+String2]; bstrString
0x180012755  call    cs:__imp_SysFreeString
0x18001275b  mov     rcx, cs:WPP_GLOBAL_Control
0x180012762  cmp     rcx, rsi
0x180012765  jz      short loc_180012785
0x180012767  test    byte ptr [rcx+1Ch], 10h
0x18001276b  jz      short loc_180012785
0x18001276d  mov     rcx, [rcx+10h]
0x180012771  lea     r8, WPP_92b4ede73d0c3990e751819403b3312f_Traceguids
0x180012778  mov     edx, 11h
0x18001277d  mov     r9d, edi
0x180012780  call    WPP_SF_d
0x180012785  mov     rbx, [rsp+38h+arg_8]
0x18001278a  mov     eax, edi
0x18001278c  mov     rsi, [rsp+38h+arg_10]
0x180012791  add     rsp, 30h
0x180012795  pop     rdi
0x180012796  retn
```
