# LaunchPrivacyURL(int)

- ea: `0x180004430`
- end: `0x180004481`
- name: `?LaunchPrivacyURL@@YAJH@Z`
- size: `81`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a880`
- `0x18000ee10`

## callees

- `0x18000b5dc`
- `0x180016c1e`

## string_xrefs

- `0x180004460`: `https://go.microsoft.com/fwlink/?LinkId=521839`

## pseudocode

```c
__int64 __fastcall LaunchPrivacyURL()
{
  _SHELLEXECUTEINFOW v1; // [rsp+20h] [rbp-78h] BYREF

  memset_0(&v1, 0, sizeof(v1));
  v1.cbSize = 112;
  v1.lpVerb = L"open";
  v1.nShow = 1;
  v1.lpFile = L"https://go.microsoft.com/fwlink/?LinkId=521839";
  return UtilLaunchURL(&v1);
}

```

## disassembly

```asm
0x180004430  sub     rsp, 98h
0x180004437  xor     edx, edx; Val
0x180004439  lea     rcx, [rsp+98h+var_78]; void *
0x18000443e  lea     r8d, [rdx+70h]; Size
0x180004442  call    memset_0
0x180004447  lea     rax, aOpen; "open"
0x18000444e  mov     [rsp+98h+var_78.cbSize], 70h ; 'p'
0x180004456  mov     [rsp+98h+var_78.lpVerb], rax
0x18000445b  lea     rcx, [rsp+98h+var_78]; struct _SHELLEXECUTEINFOW *
0x180004460  lea     rax, aHttpsGoMicroso; "https://go.microsoft.com/fwlink/?LinkId"...
0x180004467  mov     [rsp+98h+var_78.nShow], 1
0x18000446f  mov     [rsp+98h+var_78.lpFile], rax
0x180004474  call    ?UtilLaunchURL@@YAJPEAU_SHELLEXECUTEINFOW@@H@Z; UtilLaunchURL(_SHELLEXECUTEINFOW *,int)
0x180004479  add     rsp, 98h
0x180004480  retn
```
